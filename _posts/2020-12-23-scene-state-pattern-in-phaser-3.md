---
layout: post
title: State Pattern in Phaser 3
description: Is the `update` function of your scene full of chunky conditionals? Here's
  one solution.
categories: software-engineering game-dev
date: 2020-12-23 01:58 -0700
---
I am currently working on a game using the [Phaser 3 game engine.](https://www.phaser.io/phaser3) I like Phaser a lot because it handles the details of instantiating sprites and handling game objects for you, but gives enough space for you to handle things on your own. Recently I struggled with one of the scenes in my game: its `update` method grew to an enormous size, with a gnarly set of conditionals that made it hard to adjust.

I was reading [*Refactoring to Patterns* by Joshua Kerievsky](https://industriallogic.com/xp/refactoring/), and found his recipe on how to refactor one such situation to the [State pattern](https://sourcemaking.com/design_patterns/state). I thought that was a solid design pattern for my situation, as all the conditionals in `update` were meant to either perform an operation according to the current state of the scene, or to look up what the next state to transition to is. Simply put, my scene could be represented by a DFA[^1], and the State pattern is one such way to represent it.

## State Pattern

The [State pattern](https://sourcemaking.com/design_patterns/state) is a design pattern that intends is to represent a finite state machine. It is used to handle making the behavior of an object depend on the internal state of the object. A common smell that indicates a potential State pattern is the [`switch` statement or a set of chunky conditionals](^2).

The benefit of using a state pattern is that it replaces a large unwieldy set of conditionals with a small class structure, and the process of adding new behavior is simply the process of adding a subclass to the system. This means that a State pattern in the right place makes code both easier to read and easier to modify. The main drawback of the state pattern is that it makes the state machine it encapsulates implicit--a newcomer to the codebase would see a bunch of classes that all point to each other in odd ways. This could make it a lot harder to see how the state machine operates without moving through the various classes and reading their source code.

## Example

[I wrote up an example repo that illustrates the problem I was faced with, as well as a set of refactors that move to the State pattern](https://github.com/cincospenguinos/SceneStatePhaser3Example). You can look through that repo commit-by-commit to see how I refactored things into the solution I came up with, but I'll be hitting the highlights here in this post. You can also play with the game [here](https://cincospenguinos.github.io/SceneStatePhaser3Example/index.html).

### Overview

I had a simple game that moved a little bit of text around according to the current state of the scene. The state of the scene is determined with four switches, and the state changes depending on what switches are on/off during `update`. There were two parts to `update`: the process of moving, and the process of transitioning to a new state. There was a `switch` statement and a large `if-else if` tree for each of those operations, respectively:

```javascript
update() {
	let x = 0;
	let y = 0;

	switch(this.currentState) {
		case 'NO': {
			break;
		}
		case 'R': {
			x = MainScene.VELOCITY;
			break;
		}
		case 'U': {
			y = -MainScene.VELOCITY;
			break;
		}
		case 'L': {
			x = -MainScene.VELOCITY;
			break;
		}
		case 'D': {
			y = MainScene.VELOCITY;
			break;
		}
	}

	if (this.text.x < (WIDTH - this.text.width) && this.text.x > 0) {
		this.text.x += x;
	}

	if (this.text.y < (HEIGHT - this.text.height) && this.text.y > 0) {
		this.text.y += y;
	}

	if (this.currentState === 'NO') {
		if (this.switches.a.isOn && !this.switches.b.isOn) {
			this.currentState = 'R';
		} else if (this.switches.d.isOn) {
			this.currentState = 'U';
		} else if (!this.switches.a.isOn && this.switches.c.isOn) {
			this.currentState = 'L';
		}
	} else if (this.currentState === 'R') {
		if (this.switches.b.isOn) {
			this.currentState = 'NO';
		} else if (this.switches.d.isOn) {
			this.currentState = 'L';
		}
	} else if (this.currentState === 'L') {
		if (!this.switches.d.isOn && !(this.switches.a.isOn || this.switches.b.isOn)) {
			this.currentState = 'U';
		} else if (!this.switches.d.isOn && this.switches.b.isOn) {
			this.currentState = 'D';
		}
	} else if (this.currentState === 'D') {
		if (this.switches.a.isOn && !this.switches.c.isOn) {
			this.currentState = 'NO';
		}
	} else if (this.currentState === 'U') {
		if (!this.switches.a.isOn && this.switches.c.isOn) {
			this.currentState = 'R';
		}
	}
}
```

A couple things to note here:

* The `currentState` property is a string. To determine what state we are on and what we need to transition to, we need to do string comparison
* The operation behavior--that of moving--is well separated from the transition logic. A more difficult situation would have been a tight coupling between the state transition logic and the behavior logic. In that case, teasing apart the two would be needed before performing this refactoring
* There's a few global pieces here and there--`WIDTH` is the width of the screen, `MainScene.VELOCITY` is the velocity of the text when it is moving, etc.

### Step 1: Replace unsafe state type with class

If you're like me, you misspell as you type, and you and your IDE may not catch it. A way to mitigate that issue is to take encapsulate the set of unsafe types that are in use and convert them to a set of classes/enumerated type that stands in for that unsafe type. In our example, the `currentState` is represented as a string, and that could easily be replaced with a reference to an object.

I did this by replacing one of the [strings with a global object's property](https://github.com/cincospenguinos/SceneStatePhaser3Example/commit/65343becf46765658dc39e4e90652fd64b0a3ace):

```javascript
const ALL_STATES = {
	NO: 'NO',
};

/* ... */

update() {
	let x = 0;
	let y = 0;

	switch(this.currentState) {
		case ALL_STATES.NO: {
			break;
		}
		case 'R': {
			x = MainScene.VELOCITY;
			break;
		}
		case 'U': {
			y = -MainScene.VELOCITY;
			break;
		}
		case 'L': {
			x = -MainScene.VELOCITY;
			break;
		}
		case 'D': {
			y = MainScene.VELOCITY;
			break;
		}
	}

	/* ... */
}
```

I repeated this step until [I had all of the strings in a single object](https://github.com/cincospenguinos/SceneStatePhaser3Example/commit/08463a93a7cd678fdb5aff60ca9e487408e4deb7). I checked to make sure that things still worked properly after [this step](^3). Since they did, I continued to the next step.

### Step 2: Create State superclass

After [moving `ALL_STATES` to be a static property of the scene](https://github.com/cincospenguinos/SceneStatePhaser3Example/commit/133ca682ec4ac373cfbc59b0b3e6838795a7b580), I created a class that represented a movement state. It only has three properties: `x`, `y`, and `key`:

```javascript
class MovementState {
	constructor(x, y, key) {
		this.key = key;
		this.x = x;
		this.y = y;
	}
}
```

This class will be the super class of all of our individual scene states. Given that each of those scene states move either x or y some amount and need to be individually identified, I caused each of those properties to be properties of the class. I went ahead and used the class by replacing the object of states with instances of that class:

```javascript
MainScene.STATES = {
	NO: new MovementState(0, 0, 'NO'),
	LEFT: new MovementState(-MainScene.VELOCITY, 0, 'L'),
	RIGHT: new MovementState(MainScene.VELOCITY, 0, 'R'),
	UP: new MovementState(0, -MainScene.VELOCITY, 'U'),
	DOWN: new MovementState(0, MainScene.VELOCITY, 'D'),
};
```

This change required the `switch` statement on `currentState` to look at its key instead, as we set `currentState` to an instance of that class:

```javascript
/* ... */

	switch(this.currentState.key) {
		case MainScene.STATES.NO.key: {
			break;
		}
		case MainScene.STATES.RIGHT.key: {
			x = MainScene.VELOCITY;
			break;
		}
		case MainScene.STATES.UP.key: {
			y = -MainScene.VELOCITY;
			break;
		}
		case MainScene.STATES.LEFT.key: {
			x = -MainScene.VELOCITY;
			break;
		}
		case MainScene.STATES.DOWN.key: {
			y = MainScene.VELOCITY;
			break;
		}
	}

/* ... */
```

The chunky `if` statement set worked just fine, so I left it as is.

### Step 3: Replace `switch` statement with query

Since the `currentState` property is an object with `x` and `y` properties, we don't need to determine how we need to move using a switch statement. We can get away with just inlining a reference to those properties:

```javascript
/* ... */
if (this.text.x < (WIDTH - this.text.width) && this.text.x > 0) {
	this.text.x += this.currentState.x;
}

if (this.text.y < (HEIGHT - this.text.height) && this.text.y > 0) {
	this.text.y += this.currentState.y;
}
/* ... */
```

It works right out of the box because we established what those values are when we instantiated the various states.

### Step 4: Begin implementation of subclasses

We want to change the behavior of our `update` method according to the current state. We can do that by introducing subclasses of our `MovementState` class that implements the necessary behavior--in this case, transition behavior. The first step is making a new `transition(switches)` method on the super class with the default behavior of returning itself. [We then create a subclass of `MovementState` that handles one of the operations, instantiating it in place of the instantiation of the super class](https://github.com/cincospenguinos/SceneStatePhaser3Example/commit/b858791e0faf21bb79036c2004ad3a0955c66fb5):

```javascript
/**
 * Represents the state that causes movement.
 */
class MovementState {
	constructor(x, y, key) {
		this.key = key;
		this.x = x;
		this.y = y;
	}

	/** Returns the key of the state to transition to. No-op is the default behavior. */
	transition(switches) {
		return StateKeys[this.key];
	}
}

class NoState extends MovementState {
	constructor() {
		super(0, 0, StateStrings.NO);
	}
}

/* ... */
MainScene.STATES = {
	NO: new NoState(),
	LEFT: new MovementState(-MainScene.VELOCITY, 0, StateStrings.LEFT),
	RIGHT: new MovementState(MainScene.VELOCITY, 0, StateStrings.RIGHT),
	UP: new MovementState(0, -MainScene.VELOCITY, StateStrings.UP),
	DOWN: new MovementState(0, MainScene.VELOCITY, StateStrings.DOWN),
};
```

As of right now it does nothing, but that's because we're not taking advantage of the `transition` method yet. [We go ahead and implement the transition logic and perform the state change operation in `update` accordingly](https://github.com/cincospenguinos/SceneStatePhaser3Example/commit/63fbca1d56fd4a2e4009e4d388d427d933c30993):

```javascript
update() {
	/* ... */

	if (this.currentState === MainScene.STATES.NO) {
		const nextStateKey = this.currentState.transition(this.switches);
		this.currentState = MainScene.STATES[nextStateKey];
	} else if (/* ... */) {
		/* ... */
	}
}
```

I had the `transition` method return the key of the next state. This ensured that states didn't know about each other's instances, but did know about each other's identifiers. This provides a little bit more decoupling between each state.

I performed this step until I had moved each transition out to a separate subclass.

### Step 5: Clean up `update`

Since each step of the conditional performed the same operation, I simply replaced the whole conditional with that operation:


```javascript
update() {
	/* ... */

	const nextStateKey = this.currentState.transition(this.switches);
	this.currentState = MainScene.STATES[nextStateKey];
}
```

After that, the refactoring is complete, and we are left with a simplified `update` method:

```javascript
update() {
	if (this.moveX) {
		this.text.x += this.currentState.x;
	}

	if (this.moveY) {
		this.text.y += this.currentState.y;
	}

	const nextStateKey = this.currentState.transition(this.switches);
	this.currentState = MainScene.STATES[nextStateKey];
	this.text.setText(StateKeys[this.currentState.key]);
}
```

## Check out my game!

The most recent prod build of my game is always available [here](https://flower-prince-studios.herokuapp.com/gobwar). For more updates and information, check out our [discord server](https://discord.gg/6ty5Dd3).

[^1]: "DFA" here is short for ["deterministic finite automaton,"](https://en.wikipedia.org/wiki/Deterministic_finite_automaton) which is one type of a [finite state machine](https://en.wikipedia.org/wiki/Finite-state_machine).
[^2]: I recognize calling a "switch statement" a code smell is inflammatory--I mean, it's a feature of the language. Why would that be a smell? My only response is that the `switch` statement indicates that there is behavior dependent on a variable, and that can be represented either as a [Strategy](https://sourcemaking.com/design_patterns/strategy) or a [State](https://sourcemaking.com/design_patterns/state) pattern. For more about how `switch` statements can be a smell, check out [this page](https://refactoring.guru/smells/switch-statements).
[^3]: I actually made a mistake here. I caused a regression that caused the game to crash. I would have caught this if I had this behavior wrapped in a set of automated tests that I could rely on to make sure that every little change I make didn't break anything. Since this was (1) a toy example, and (2) I haven't found a good way to test scenes in Phaser 3 yet, I simply double-checked my work and QA'd after each little step. Regardless, an automated test suite that captures all the little cases you are changing is the ideal way to do a heavy refactoring like this.