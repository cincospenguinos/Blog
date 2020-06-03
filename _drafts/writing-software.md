---
layout: post
title: Writing Software
description: DHH gave an inflammatory talk a few years ago, and I have some thoughts about it.
categories: software-engineering
---

<blockquote>
	<p>'There is still one of which you never speak.'</p>
	<p>Marco Polo bowed his head.</p>
	<p>'Venice,' the Khan said.</p>
	<p>Marco smiled. 'What else do you believe I have been talking to you about?'</p>
	<p>The emperor did not turn a hair. 'And yet I have never heard you mention that name.'</p>
	<p>And Polo said: 'Every time I describe a city I am saying something about Venice.'</p>
	<footer>--Italo Calvino, <cite>Invisible Cities</cite></footer>
</blockquote>

In 2014 David Heinemeier Hansson (DHH) gave a talk in Chicago for 2014's Rails conference, simply entitled ["Writing Software."](https://www.youtube.com/watch?v=9LfmrkyP81M) DHH made a number of remarks in that talk that others found inflammatory. Given DHH's reputation online, it's not terribly surprising that he would find himself embroiled yet again in another conflict over the expression of his thoughts on software engineering.


[Here's the link](https://www.youtube.com/watch?v=9LfmrkyP81M)

### Further Reading

* DHH quotes [this white paper](https://rbcs-us.com/documents/Why-Most-Unit-Testing-is-Waste.pdf) on why unit-level testing is waste

### Notes on Talk

* The barrier of entry into programming
	* DHH feels like he learned to program late
	* DHH wrote little pieces of code as a kid to respond to problems--pretty neat, really!
	* [This isn't really programming](https://youtu.be/9LfmrkyP81M?t=290)
		* I disagree with this statement! It was programming! He made something small that solved a real-world need!
		* His solution was clunky and archaic, it was lacking in usability, but it was something he made!
		* Don't diminish your young self's attempt there, man
	* Attempts to make things are hard--required understanding technical things like mathematics and computer science
	* [DHH failed to identify with the computer science paradigm](https://youtu.be/9LfmrkyP81M?t=624)
		* Computer Science doesn't appeal to DHH--doesn't make sense
		* Learning programming through the lense of hard science didn't click for him
		* He was disappointed--discouraged, even--because of that barrier of entry
		* Disabused him of the notion of making discoveries in computer science
		* It was a relief--he knew he wasn't going to be what he was going to do. He wanted to build things, not simply solve puzzles
* Aspiration of the industry is that we're all computer scientists
	* "We're all computer scientists"--not true, according to DHH
	* Most programmers think of themselves as colleagues with Linus Torvalds
		* Linus would thoroughly disagree, according to DHH
		* It's a bummer to pick your heroes poorly
	* "Most information system development has little to do with the science part of computer science"
	* Being a great programmer of information systems is not the same as being a computer scientist
	* Being a great computer scientist is not the same as being a great programmer of an information system
* Looking at programming as a hard science is counter-productive
	* Characterizes the common software engineering approach of mocking the analysis of literature
	* Carrying that attitude into programming yields ideas like "Law of Demeter"
		* Projections of the laws of the world and the nature of code
	* Observing programming is more like literature
		* It's subjective analysis of someone else's thoughts
		* That's bonafide literature analysis
	* Software engineering is subjective analysis and expressions of things
	* You can fool yourself into believing that you found laws for things that aren't there
		* That's the definition of pseudoscience
		* A lot of things DHH sees are pseudoscience
* Software developers are exactly like people who try to cheat the basics
	* DHH uses a metahpor of dieting here
	* Everyone would love to have their codebase "be clean"
		* We're all a little insecure about our bodies periodically; we're all a little insecure about our bodies sometimes too
		* "You're not a professional until you follow this one weird tip"
		* Hits people right in the "Imposter plexus"
	* Everyone needs to follow patterns and practices to be a good programmer
* "TDD is the most successful software diet of all time"
	* Test first! Test Driven Design!
	* "It just didn't work" -- DHH
		* Driving his design is not better in his mind
		* Just because people are doing TDD is wrong doesn't mean that there's something wrong with TDD
		* ["[TDD] keeps people in the perpetual state of feeling inadequate"](https://youtu.be/9LfmrkyP81M?t=1587)
	* Buy more books, attend more conference talks, run back through the loop
* Dependency injection example
	* Person age class "is dirty" because it relies on this global object that you're stubbing out and shit!
		* I dispute his claim that TDD proponents would call this dirty. TDD is what it says on the tin--write your tests before you write your code. The net effect of all of those things is beneficial
		* Conflating TDD with good design and testing practices is not a good look homie
		* The dependency injection adjustment he proposes isn't that impressive of a change. Changing that for the sake of it is not awesome, I agree.
		* Oh I see what he means. It's easier to test--not necessarily easier to reason about. I'd still dispute that design decision though
	* "Is it easier to test" is a shitty measure of success
* Rails controller example
	* I actually prefer his PersonCreationCommand in this example. I think the naming is awful--why are you using the term command in your name here homie--but encapsulating that logic for the purpose of more robust testing is quite valuable
	* Renaming that call to something else would be helpful
	* Then again, extracting this logic out may not have been ideal, depending on what is most needed in the codebase at the time. Is clarity more valuable, or speed? Extracting the chunky logic into a faster set of unit tests would save us some money with our CI usage
	* "Tests were supposed to support us, not be the main thing"
		* I thoroughly agree with that statement, but I'm not with DHH on the details of its implementation here
		* Making your code easier to test is improving the code. When you do or don't make those decisions depends wholly on what stage your application is in and what you are valuing in the moment
		* I stand with what Michael Feathers said in "Working Effectively With Legacy Code"--if your test takes more than 100ms to run, it's a slow test and work to improve it would be valuable
		* I've actively avoided making changes in an area because their tests are slow. Making your life as an engineer more enjoyable with extra work in the short term is valuable
* "TDD is focused on the unit" --DHH
	* Except it's not, dude: it's writing your tests first. What level of granularity is wholly dependent on the programmer. What level of granularity is subject to debate, depending on what your application is doing and what exactly you need it to do
	* "Driving your design from unit tests is not a good idea" --DHH
		* Maybe, maybe not. Again, it all depends on what is most valuable to the programmer and to the application at the time
		* Driving with an integration-level test can get you moving, but gutting a large amount of integration-level specs into a set of smaller unit-level specs may be a wise investment if you're spending $20 every time Circle CI does a build for you
	* "You can make anything fast if it doesn't have to work" --DHH
	* DHH gave this anecdote on losing data because the system-level tests in place to catch a bug before it went into prod
		* This point I think is decent, actually: it shows that there are benefits to system-level tests. The downsides of system-level tests though is that they can be slow. Sacrificing a bit of time for a system-level test may be a valuable investment, however, since it can catch the seams of things better than the operation of the individual things
* "Give up the need for hard-science experiments, float freely with the world"
* "Coverage, Ratio, and Speed"
	* A lot of people care about these things and these things only
* "If you can't measure something, you can't understand it. If you can't understand it, you can't control it. If you can't control it, you can't improve it."
	* "Just because something is easy to measure doesn't mean it's important."
* "Programming information systems is more like french poetry than physics." --DHH
	* This is a statement I thoroughly agree with
* "Driving your design through testing rarely has value" --DHH
	* Man, I thoroughly disagree here. Who made those design decisions? If the design is bad from you testing it, who made those decisions?
* We're wearing the wrong hat most of the time
	* If we're not engineers, what are we when we are doing something?
	* We're software writing. Writing is a much more apt metaphor than what we are doing
	* Writing is about clarity--presenting information and motivations in an understandable way
	* Clarity is about being succinct without being terse
	* He compares common TDD practices and principles to "adding more semicolons" or "adding an extra sentence in the middle of a paragraph" when that's simply not the case
		* To follow his metaphor, I'd argue that most TDD practices are about the process of rewriting. You have an idea in your mind (what you want the computer to do,) you make an assertion about what that thing is (getting it out on paper,) and then you rewrite it until it does what you want it to do. Oftentimes writing is a practice of exploring a thought in your mind and making sense of it--it's a creative process that requires work and rework to develop.
	* Clarity should be the ideal of a code base.
		* I do agree with that statement. It's open to interpretation, and that's what I like about it
* Developing an eye for clarity is what is needed
	* I think this metaphor is good too! Read a lot of code, write a lot of code, just as one would become a good writer.
* "90% of everything is crap"
	* No truer statement has been made
* The size of something not mattering if it's readable
	* The size of something matters when it hinders understandability
	* That's why it's a code smell
* Draft and redraft things
	* The act of rewriting in software is the process of refactoring--renaming variables, renaming functions, renaming classes, extracting variables, methods, classes
* Omit needless words
