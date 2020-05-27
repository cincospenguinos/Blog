---
layout: post
title: "On Code Comments"
description: "Should you use them? Short answer: no. Long answer: nooooooooooooooooooooooooooooooo. Fight me."
categories: software-engineering
---

I frequent a popular forum dedicated to making jokes about programming. The jokes shared there are usually inoffensive (and some of them are downright relatable,) but periodically I'll find one that gets under my skin. Today it was this one:

<div class="image-container"><img alt="Garbage joke for garbage programmers" src="/blog/assets/images/code-comments-meme.jpg" /></div>

I've noticed that jokes like this tend to get a lot of traction and a lot of supportive comments, while comments that express opposition to the sentiment tend to get heavily ridiculed. I can't help but find this demoralizing. Why? Because it operates from the premise that code exists to tell computers what to do.

## But that's what code is, right?

Imagine you're the new software engineer at a company. They have only one engineering position--you--and the guy before you was the guy who wrote the entire code base. Your job is to make changes to that software to keep the company moving. To most people, your job is to tell computers what to do.

Here's the problem: the guy before you didn't think about somebody having to read or understand the code he wrote--his job was to tell the computer what to do. So he left this gnarled mess that is hopelessly opaque, with [code smells](https://martinfowler.com/bliki/CodeSmell.html) so bad they'll make you vomit. We've all seen (and I'm sure we've all written) code just like it.

It would be infuriating to be put in this position. You have no knowledge of how this thing works, and you're expected to ship a half-dozen bugfixes by the end of the week. You can go through the troublesome process of changing things to figure out what things are, but trial and error is tedious and time consuming. You could go line-by-line and figure out what exactly the computer is doing, but that's a massive pain in the ass. Your ability to do your job is now dampened by the previous guy's inability to communicate.

I was that guy once, and I cursed the guy before me. I was also the guy before me, and I cursed him too. I imagine there's another poor soul who's looking at my code from two years ago right now, promising that if he ever finds me he will end me for that ugly two-hundred line method I wrote that I knew was trash, but checked in anyway because I had a few little comments sprinkled in to explain some of the more obtuse parts.

I hated that position. I still hate that position. It's a position that exists because of that premise, that dogma: code exists to tell computers what to do. If that were true, we would still be content writing machine code. If that were true, the previous engineer who wrote the thing would be blameless for his garbage work. And you would be blamed for your poor performance, in spite of that performance being due to the poor decisions and poor communication of the previous guy.

Now imagine that littered throughout it there all these little comments that say things like `/* Fixes #10928 */` or `// Iterates through the list and updates orders to match batch sizes`. Is the code any cleaner, simpler, or maintainable? No, it's not--the code is still hard to read. All those comments do is either clutter the code base or pass off ugly code as acceptable because a little comment explains what it does.

So what's the solution to this problem? Is it more comments?

## No. No it's not.

Consider the following example. It's [fizz buzz](https://en.wikipedia.org/wiki/Fizz_buzz), but with comments:

```java
/* ... */
// We're going to print fizz and buzz here
for (int i = 1; i <= 100; i++) { // Threshold is 100
	if (i % 3 != 0 || i % 3 != 0) { // Print out numbers that are not multiples of three or five
		System.out.println(i);
	}

	if (i % 3 == 0 && i % 5 == 0) { // Divisible by 3 or 5
		System.out.println("FizzBuzz");
	} else if (i % 3 == 0) { // Divisible by 3
		System.out.println("Fizz");
	} else if (i % 5 == 0) { // Divisible by 5
		System.out.println("Fizz");
	}
}
/* ... */
```

"Hey," you might say, "those comments are good! They're telling me what the `i % 3 == 0` means, and that's really helpful!" Sure, those comments explain those things, but there's other ways to communicate that information without a comment. Consider this next example:

```java
private static final int FIZZ_BUZZ_THRESHOLD = 100;
/* ... */
printFizzBuzz();
/* ... */

private void printFizzBuzz() {
	for (int numberToTest = 1; numberToTest <= FIZZ_BUZZ_THRESHOLD; numberToTest++) {
		boolean divisibleByThree = numberToTest % 3 == 0;
		boolean divisibleByFive = numberToTest % 5 == 0;

		String message = fizzOrBuzzOrNumber(numberToTest, divisibleByThree, divisibleByFive);
		System.out.println(message);
	}
}

private String fizzOrBuzzOrNumber(int number, boolean divisibleByThree, boolean divisibleByFive) {
	boolean notARelevantMultiple = !divisibleByThree && !divisibleByFive;

	if (notARelevantMultiple) {
		return Integer.toString(number);
	}

	String fizzBuzzOrBoth = "";

	if (divisibleByThree) {
		fizzBuzzOrBoth += "Fizz";
	}

	if (divisibleByFive) {
		fizzBuzzOrBoth += "Buzz";
	}

	return fizzBuzzOrBoth;
}
```

I made several changes in this second example that I think illustrates my point: the comments in the first example could be represented in other ways. Let's pick them apart:

* I labeled the whole thing with a method name. Instead of saying `We're going to print fizz buzz here`, it's in the name of the method--literally just `printFizzBuzz`. And that method does what it says it does--no need to interpret anything; the message is clear.
* There was a limit to our fizz buzz loop. There's probably a reason for that to exist, but just a magic-floating `100` isn't very descriptive. If I needed to change it, I'd have to know that `100` was the magic number that stopped iteration. Extracting that number out to a separate variable gives context for that number--it's a threshold that fizz buzz needs to stop at.
* Instead of using `i`, I used the name `numberToTest`. Again, the variable name is descriptive: it's not just some throwaway `i`. It's a number that needs to be checked, evaluated, and eventually a decision needs to be made according to its characteristics.
* I extracted two variables: `divisibleByThree` and `divisibleByFive`. Those variables say exactly what characteristics about `numberToTest` we care about: is it divisible by 3 or by 5? It takes that more alien modulo syntax understandable by the compiler and gives a nice label to it that's understandable to a person.
* I pulled out the decision-making step into a separate method. It's only 16 lines long and is pretty straightforward. It outlines clearly the case of a number whose value is not a multiple of three or five, and contains the logic around printing "Fizz" or "Buzz" or both. If we needed to adjust that logic, it's all right there, with pretty labels to read on what everything is doing and why.
* The original method is clean as a whistle--it's a loop, a couple variables, a call to a private method, and a print statement. There's no ambiguity as to what is happening--it's all right there in easy-to-digest chunks of prose in camel case.

What's the downside to this approach? There's more code doing the same thing, and... that's it. That's the only downside--the fact that it takes up a few more bytes on my hard drive.

If we are worried about the size of the code file, then (1) why are you programming it in Java, and (2) are you sure Java was the right thing to write it in? Maybe the thing should be written in something higher, like Ruby, or lower, like assembly. Or maybe you need different compiler options than what you're using--[flags for those exist, even in Java](https://www.oracle.com/java/technologies/javase/vmoptions-jsp.html#PerformanceTuning). The solution to "hey this code is hard to understand" isn't a comment--it's more expressive design, built on the bricks of well-selected variable and method names.

I'm hardly the first one to point this out--[Uncle Bob](https://blog.cleancoder.com/) explains this well in his book [Clean Code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM/ref=sr_1_3?dchild=1&keywords=Clean+Code&qid=1590558884&sr=8-3). As he even says in his book, "Comments do not make up for bad code." (*Clean Code*, page 54.)

## The last guy did not do his job

He told the computer what to do. He did not tell you what the computer was told to do. The dogma mentioned earlier is only half of our job--we write code to tell the computer what to do *and* to tell people what the computer is doing. Code that is understandable but does not work is worthless. Code that works but is not understandable is equally worthless.

## When should I use a comment?

A well-placed comment can be valuable, particularly when it's expressing something that code can't. Perhaps a legal requirement forced one design or algorithm over another. A quick `TODO` comment to remind you to come back to something before checking your work in could be helpful. In each of these cases, a comment is written when the programmer fails to express something through the code itself.

A comment should never be used to explain what is being done--code exists for that. It also should generally not explain why something was done--version control messages exist for that. Comments should be used with great care and forethought, all for the purpose of upholding the second half of our job: to explain to a human what the computer is doing.

A comment explaining a gnarly piece of code is just as valuable as spraying a bit of Febreze on your rotting garbage--it's an attempt to hide the smell, but trust me: you're not fooling anyone. **Comments do not make up for bad code.**
