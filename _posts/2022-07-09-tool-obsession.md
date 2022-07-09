---
layout: post
title: Tool Obsession
description: Just because you can doesn't mean you should.
categories: software-engineering technology
date: 2022-07-09 10:24 -0600
---
As part of my studies, I stumbled on a very brief short story by Jorge Luis Borges. It's quite short, so you can read it here[^1]:

<blockquote>
	<p>...In that Empire, the Art of Cartography attained such Perfection that the map of a single Province occupied the entirety of a City, and the map of the Empire, the entirety of a Province. In time, those Unconscionable Maps no longer satisfied, and the Cartographers Guilds struck a Map of the Empire whose size was that of the Empire, and which coincided point for point with it. The following Generations, who were not so fond of the Study of Cartography as their Forebears had been, saw that that vast Map was Useless, and not without some Pitilessness was it, that they delivered it up to the Inclemencies of Sun and Winters. In the Deserts of the West, still today, there are Tattered Ruins of that Map, inhabited by Animals and Beggars; in all the Land there is no other Relic of the Disciplines of Geography.</p>
	<footer>--Suarez Miranda, <cite>Viajes devarones prudentes, Libro IV,Cap. XLV, Lerida, 1658</cite></footer>
</blockquote>

Borges wrote this story himself, but attributed it to Suarez Miranda, a man that never existed in the year 1658. The moment in history Borges refers to in the story is one of dramatic change and discovery--European powers colonizing the New World. Maps were important then--perhaps even enough so to give cartographers an enormous amount of power and money.

Most humorous about this story is how it exposes an irony about cartography. A map's function is to make small what is big: to be able to see and reason about a large geographical space in the comfort of your armchair. A 1:1 map no longer serves that function. You can't hold it and see at a glance what the space it represents is; you'd have to spread it out and wander around. That means the perfect 1:1 map of the Empire is useless.

Why would cartographers make something so useless? Simple: they were obsessed with their tools.

## So I started a job working in Golang...

...and I have to confess that I was initially unimpressed with it. I'm from a Ruby background, and the things people dislike about Ruby I actually enjoy. I like the looseness of the duck-typing system, how simple syntax is, its shameless embrace of object-orientedness, and its emphasis on programmer enjoyment. If I'm given a task and I can use whatever language I want, I generally pick Ruby because it fits well in mind's hand.

A close friend of mine started a similar job around the same time as I did. He's using Golang, and he loves it. He sung its praises to me when we met for dinner one evening, pointing out how fast it is thanks to compilation, how nice it is relying on a static type system, how well it handles concurrent applications, and how it doesn't include most object-oriented features I've come to love. 

Our conversation led to a larger discussion of what makes a programming language "good." Golang has stripped away many of the features of the past thirty years, and in the process requires programmers to return to procedural designs and patterns. In Golang, one can't simply throw an exception anymore--errors need to be returned, checked, and passed around. No `extends` keyword makes code reuse a bit of a challenge, and (up until recently) a lack of generics has forced a lot of code duplication.

Removing these features had their benefits too though. Many programmers tend to abuse class extension, opting to extend a class instead of simply aggregating. Having code throw an exception you were not anticipating or was not documented to be able to be thrown can case enormous headaches, and so forcing errors to be mentioned and returned and handled as they arrive ensure that they are always on the programmer's mind.[Watching this explanation of Golang's philosophy](https://www.youtube.com/watch?v=sX8r6zATHGU) filled in a lot of the details surrounding why its designers made the decisions they did.

## Freud's Observations on Tech

In _Civilization and Its Discontents_, Sigmund Freud outlined the stages in which a civilization develops. Tool development, he argues, is the first stage, stating "With every tool man is perfecting his own organs, whether motor or sensory, or is removing the limits to their functioning."[^2] He outlines a few examples, finally stating "Man has, as it were, become a kind of prosthetic God."[^3] The purpose of tools, according to Freud, is to extend the abilities of man, moving one's abilities to greater and higher powers. He also mentions, however, that "those organs have not grown on to [man] and still give him much trouble at times."[^4] The tools we create can be helpful, but also, at times, cumbersome, or improperly matched to the current problem. What benefit of a prosthetic foot if what you need to do your job is a hand?

I can't help but see this struggle everywhere in tech. I'm not the first person to mention that [blockchain is an incredible technology that solves almost no problems](https://thecorrespondent.com/655/blockchain-the-amazing-solution-for-almost-nothing), and although it appears promising in the abstract, [the amount of power it needs is absurd](https://digiconomist.net/bitcoin-energy-consumption), making it an unsavory solution to virtually any problem.

After learning a number of different programming languages, I can't say that they're all created equally either. Would I need something as sophisticated as Rails for a static webpage? Probably not.

## "I heard that programming language sucks."

[Early](https://www.reddit.com/r/ProgrammerHumor/comments/hqzrdx/does_it_sucks/) [programmers](https://www.reddit.com/r/ProgrammerHumor/comments/c3u0wn/css_sucks/) [tend to complain](https://www.reddit.com/r/ProgrammerHumor/comments/qkzpei/oh_no/) [about this or that language](https://www.reddit.com/r/ProgrammerHumor/comments/f5nta8/whenever_i_start_learning_a_new_language_i_notice/). I was no different. I vowed as a young undergrad that I would never, ever work in C++ because it was the absolute worst, only to find myself working in it a few years later and coming to appreciate it in its own right.

I grew out of it because, over time, I've tackled enough problems in enough places and sitautions that I've discovered that, just as certain prosthetic limbs fit ourselves better than others, different toolsets fit our minds better. I have my most favorite and least favorite languages, but I think it's reasonable to say that languages with decent adoption rates and sizable applications built out of them are capable of doing _something_ valuable, and can fit a programmer and problem better than any other. The tools of a woodworker are highly contextual, and so are ours. Claiming that a programming language sucks betrays a lack of experience with that language, not an honest assessment of the tool's usefulness.[^5]

[^1]: This story is _On the Exactitude of Science_ by Borges. I found this version online [here](https://kwarc.info/teaching/TDM/Borges.pdf).
[^2]: Freud, _Civilization and Its Discontents_, pg. 37 of my edition. [Here's another one I found](https://www.stephenhicks.org/wp-content/uploads/2015/10/FreudS-CIVILIZATION-AND-ITS-DISCONTENTS-text-final.pdf). It's in chapter 3.
[^3]: Ibid, pg. 38-39
[^4]: Ibid.
[^5]: I wrote this article mostly for my younger self who once, on the job as a full-stack engineer, complained about how bad CSS sucked, only to have my own ignorance with CSS demonstrated to me by a senior engineer on my team. Reflecting on that moment while reading Borges inspired this post.
