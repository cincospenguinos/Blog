---
layout: post
title: Writing Software
description: A response to DHH's 2014 talk of the same name.
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

In 2014 David Heinemeier Hansson (DHH) gave a talk in Chicago for that year's Rails conference, simply entitled ["Writing Software."](https://www.youtube.com/watch?v=9LfmrkyP81M) DHH made a number of remarks in that talk that others found inflammatory. Given DHH's reputation for getting into arguments on the internet--he even admits that openly in his talk--it's not terribly surprising that he would find himself embroiled yet again in another conflict over the expression of his thoughts on software engineering.

In spite of the coarseness of some his delivery, I found some valuable pieces of information about Software Engineering and the industry at large through his talk. There's a number of things he discusses that resonated deeply with me, and others that left me bewildered and thoroughly disappointed. Forgive how messy this post may be; it's hard getting all of my thoughts in order on this subject.

[Here's the link](https://www.youtube.com/watch?v=9LfmrkyP81M)

## The Barrier of Computer Science

As you can see from my [resume]({{site.baseurl}}/resume), I have a bachelor's of science in Comptuer Science from the University of Utah. The U of U has an impressive Computer Science program, and many within the state would see that as an impressive accomplishment. Within the program I ended up [implementing my own machine learning library in Ruby](https://github.com/cincospenguinos/CS5350), [tackling challenging NLP problems](https://github.com/cincospenguinos/NLP), and [exploring aspects of statistics and probability within the language R](https://github.com/cincospenguinos/cs3130). At a glance, I've tackled some exceptionally technical problems within the field of Computer Science itself.

What you may not know is that it took seven years to make it through, even with an abundance of college credits that allowed me to skip over most general coursework. It took me so long to get through because I didn't feel totally comfortable as a Computer Science major.

Initially I studied Music Composition in college, completing up through some junior-level coursework within that degree. Later I started double-majoring in French Literature (er, French with an emphasis on literature.) In each of those schools I felt so much more comfortable than in Computer Science. I liked Computer Science, I liked my professors, I liked the coursework, but I felt the general attitude towards the kind of work I wanted to do was inherently not-creative, dry and overly scientific.

I felt so much happier reading French novels and writing papers exploring their meanings than building that ML library. I enjoyed the process of examing language, exploring meaning, and enjoying the raw expression of storytelling in a beautiful way. I've always been much more comfortable in the liberal arts sphere of things and its inherent humanity than in the cold, rigid space of scientific reasoning and understanding.

Why did I get a computer science degree? I wanted a job. I wanted a job where I sat and wrote code all day, and that was an easy way to make college be that means of entry. I loved taking problems and writing code to solve them, but I loved writing papers and responding to interesting thoughts and ideas a whole lot more. Experimenting on the powers and limitations of computation was interesting, but I don't feel that I have a mind for it quite like other folks.

And yet, I love my job. I would have become a programmer regardless of whether or not I got a computer science degree, or even whether or not I got a job programming. I love it most because of how human my current employer makes it. To write code is to communicate an idea, with the nice benefit of creating something of use to someone else.

## The Aspirations of the Industry

DHH observed in his talk that folks who work on building information systems tend to think of themselves as colleagues with computer scientists. He brings out Linus Torvalds as an example. I do agree that a lot of industry folks tend to think of themselves as pushing boundaries and limits of computer science, but I would ultimately disagree with his example calling Linus Torvalds a computer scientist.

I readily admit that I could be speaking out of ignorance here, but I would not call Linus Torvalds's work a classic example of computer science. That doesn't mean his contribution is in any way insignificant--he made a highly complex piece of software that the vast majority of the web runs on today. He made another complex piece of software that makes the process of creating and maintaining software far easier than virtually anything else on the market at the time. As far as Mr. Torvalds's work goes, he has made significant contributions that can't be underemphasized.

He didn't solve the Traveling Salesman problem though, proving that P=NP. Conversely he hasn't proved that `P != NP`. He hasn't proposed a new abstract model of computation that pushes past the boundaries of the Turing Machine. At the end of the day, he wrote some code that enabled a lot of other people to either better maintain their own code or use a free and open-source operating system to be used for a variety of things, lowering the monetary boundary of entry into computing.

Holding him up as an example of "being a computer scientist" isn't the best example because his work doesn't quite fit in the realm of computer science.

### Or does it?

My current employer recently ran into a challenging problem. They needed to find a way to implement a requested feature, and discovered that the feature was a form of the Traveling Salesman problem. My coworkers tackled that problem, woring diligently, reading academic works in the field of computer science that explored heuristics to the Traveling Salesman problem and came up with a solution that ended up being a synthesis of the various works my coworkers read.

Is that not computer science? Is that not tackling a problem using a computing machine and attempting to solve that problem in a human beneficial way? Is that not exploring the boundaries and limitations of the computational space? Perhaps what my coworkers did was not on the surface computer science--at least in the academic sense--but they were exploring boundaries and limitations of computability, and it happened to benefit the company as a whole to do such.

There's a reason the engineering department of my current employer is called "Research and Development." As odd as it is seeing a branch hold that label in an organization whose express purpose is to make money, the process of making a machine do something can and does at times bump into situations where exploring computational limits is necessary.

### So is Mr. Torvalds a Computer Scientist?

I don't know. On the surface, maybe not. I imagine he still had to deal with a variety of unsolved problems though while writing the Linux kernel or coming up with Git. I can imagine some algorithms that process graphs were used in the development of Git. Mr. Torvalds probably read academic works dealing with processing graphs in order to optimize his own solution. The short of it is that the creation of an information system does not always exclude the development or even use of ideas and work done within the field of computer science. I think that fact alone makes it reasonable to refer to my coworkers as my colleagues, and although I may not have the chops of Mr. Torvalds, he and I still operate in a similar space doing similar things. That, by definition, makes us colleagues.

## Software Engineering != Computer Science

I thoroughly agree with DHH on this point. The development of software is not equivalent to Computer Science, and looking at software development through the lense of Computer Science, though helpful, is not necessarily accurate. Computer Science is a science--it is rigid, it is firm, it seeks out absolute ideas about the world, and in many ways is closely connected to Mathematics. Software Development and Engineering is more human-focused. An efffective software engineer needs to be able to communicate well, both in the context of code and in the context of office interaction. Software engineering cares less about pushing forward the boundaries of computation, and more about the creation of software to solve human-centric needs.

Although a number of folks love to poke fun at [how uncaring a business may be about the science](https://xkcd.com/664/), I would argue that the academia of Computer Science and the business of Software Engineering have a symbiotic relationship. The creation of software to fill human needs brings up opportunities to explore and expand on the science itself. After all, my coworkers took a real-life problem, reduced it down to the Traveling Salesman problem, and then used academic research on that problem to solve the business's needs.

That doesn't mean the two are the same though--more like the two tend to dance together, sometimes working as inseparable tango dancers, sometimes dancing by themselves. After all, the work of having a computer solve a human problem does not usually bring up issues that require rigorous scientific reasoning and peer review. The fact that they can does not mean that they always do.

### Why view Software Engineering in a scientific lense?

I agree with DHH--I think that viewing the process of creating software as an inherently scientific discipline is inaccurate and leads to problems. I think that a lot of programmers have dogmatic attitudes about what is and is not acceptable. A quick glance at the [C++ forums](http://www.cplusplus.com/forum/) will be full of people arguing over whether one convention of brackets or tabbing or spacing is better than another (a debate that I see about as worthwhile as a pissing match.) Attempts to make things "laws" like "The Law of Demeter" don't actually improve code--they make subjective observations about software the definition of what is good and virtuous. DHH calls that pseudoscience; I call that dogma.

Scientific dogma is hardly new. [Race science](https://www.facinghistory.org/holocaust-and-human-behavior/chapter-2/science-race) is a prime example of dogmatic approach to scientific reasoning, wherein the underlying assumption was that "race is a biological phenomenon" and scientific experiments simply continued from that standpoint.[^1] A number of prominent scientists are attempting to [make scientific reasoning the only accepted philosophical approach and practice](http://existentialcomics.com/comic/190), which is in and of itself a dogma as well.

### Further Reading

* DHH quotes [this white paper](https://rbcs-us.com/documents/Why-Most-Unit-Testing-is-Waste.pdf) on why unit-level testing is waste
* Martin Fowler points at the [testing pyramid](https://martinfowler.com/bliki/TestPyramid.html)

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

[^1]: Race science has about as much to do with science as the Java has to do with Javascript: it doesn't. For a wonderful examination of the cultural construct of race and whiteness in particular, listen to the podcast [Seeing White](https://www.sceneonradio.org/seeing-white/) published by Scene on Radio.