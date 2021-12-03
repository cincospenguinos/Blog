---
layout: post
title: Tool Obsession
description: Just because you can doesn't mean you should.
categories: software-engineering technology
---

As part of my studies, I stumbled on a very brief short story by Jorge Luis Borges. It's short, so I'm placing it here[^1]:

<blockquote>
	<p>...In that Empire, the Art of Cartography attained such Perfection that the map of a single Province occupied the entirety of a City, and the map of the Empire, the entirety of a Province. In time, those Unconscionable Maps no longer satisfied, and the Cartographers Guilds struck a Map of the Empire whose size was that of the Empire, and which coincided point for point with it. The following Generations, who were not so fond of the Study of Cartography as their Forebears had been, saw that that vast Map was Useless, and not without some Pitilessness was it, that they delivered it up to the Inclemencies of Sun and Winters. In the Deserts of the West, still today, there are Tattered Ruins of that Map, inhabited by Animals and Beggars; in all the Land there is no other Relic of the Disciplines of Geography.</p>
	<footer>--Suarez Miranda, <cite>Viajes devarones prudentes, Libro IV,Cap. XLV, Lerida, 1658</cite></footer>
</blockquote>

A map's function is to make small what is big, to be able to see and reason about a geographic space upon a much smaller plane. A 1:1 map is useless in the sense that it no longer serves its function. You can't hold it and see at a glance what the space it represents is; you'd have to spread it out and wander around in it. In the process of doing that you're interacting with something more akin to VR than a map, and even then not terribly well. Why would the cartographers make a map that is useless? Simple: they were obsessed with their tools.

## So I started a job working in Golang...

...and I have to confess that I was initially unimpressed with it. I'm from a Ruby background, and the things people dislike about Ruby I actually enjoy. I like the looseness of the duck-typing system, the simple syntax, the unabashed object-oriented approach, the emphasis on programmer enjoyment. If I'm given a task and I can use whatever language I want, I generally pick Ruby because it fits well in the hands of my mind.

A close friend of mine started a similar job around the same time as I did. He's using Golang, and he loves it. He sung its praises to me when we met for dinner one evening, pointing out how fast it is thanks to compilation, how nice it is relying on a static type system, how well it handles concurrent applications, and how it doesn't include most object-oriented features I've come to love. 

Our conversation led to a larger discussion of what makes a programming language "good." Golang has stripped away many of the features of the past thirty years, and in the process requires programmers to revert to procedural patterns in various ways. On the other hand, by removing most of the features that programmers tend to abuse—class extension and exception throwing—issues stemming from the abuses of such features go away. [Watching this explanation of Golang's philosophy](https://www.youtube.com/watch?v=sX8r6zATHGU) filled in a lot of the details surrounding why it does what it does.

I wandered away from my research and our conversation with an appreciation for Golang, recognizing that it has a certain perspective that, although is different than the one I feel most comfortable with, is valuable in and of itself. If I needed a highly concurrent application with a small domain and needed to be blazing fast, I'd probably pick Golang.

As it turns out, one of the founders of my company ended up having to make that decision. The first version of our product was written using Rails and required a number of fancy image processing operations. He hit a bottleneck in the development of a core feature, and found that Rails was the culprit. After digging a bit deeper into the needs of the project and available tools at his disposal, he rewrote the entire application in Golang[^2].

## Freud's Observations on Tech

In _Civilization and Its Discontents_, Sigmund Freud outlined the stages in which a civilization develops. Tool development, he argues, is the first stage, stating "With every tool man is perfecting his own organs, whether motor or sensory, or is removing the limits to their functioning."[^3] He outlines a few examples, finally stating "Man has, as it were, become a kind of prosthetic God."[^4] The purpose of tools, according to Freud, is to extend the abilities of man, moving one's abilities to greater and higher powers. He also mentions, however, that "those organs have not grown on to [man] and still give him much trouble at times."[^5] The tools we create can be helpful, but also, at times, cumbersome, or improperly matched to the current problem. What benefit of a prosthetic foot if what you need to do your job is a hand?

I can't help but see this struggle everywhere in tech. I'm not the first person to mention that [blockchain is an incredible technology that solves almost no problems](https://thecorrespondent.com/655/blockchain-the-amazing-solution-for-almost-nothing), and although it has its peculiar uses, [the amount of power it needs is absurd](https://digiconomist.net/bitcoin-energy-consumption), making it an unsavory solution to virtually any problem. Learning a number of different programming languages, I can't say that they're all created equally either. They all _could_ be used to create a fancy image processing web application, but would Rails be performant enough for such a thing? I think Elixir and Phoenix are neat tools, but do I need it running in a Docker container with the latest greatest libraries for my little static webpage? Probably not.

## X Programming Language Sucks!

[Early](https://www.reddit.com/r/ProgrammerHumor/comments/hqzrdx/does_it_sucks/) [programmers](https://www.reddit.com/r/ProgrammerHumor/comments/c3u0wn/css_sucks/) [tend to complain](https://www.reddit.com/r/ProgrammerHumor/comments/qkzpei/oh_no/) [about this or that language](https://www.reddit.com/r/ProgrammerHumor/comments/f5nta8/whenever_i_start_learning_a_new_language_i_notice/). In my experience, that's something that we grow out of because we tackle enough problems in enough places and situations to discover that just as certain prosthetic limbs fit ourselves better than others, different toolsets fit our minds better. I have my favorite and least favorite languages, but I think it's reasonable to say that languages with decent adoption rates and sizeable applications built out of them are capable of doing _something_ valuable, and can fit a programmer and problem better than any other. The tools a woodworker uses is highly contextual, and so are ours.

That being the case, it would be wise to select the tool that fits the job, rather than the tool that you like most. I'm certainly guilty of making poor judgement calls in that sense—hence this blogpost—and I think we'd all be doing ourselves and our businesses a better service if we pick the tools and frameworks and libraries for the right job, not necessary the one we want to use.[^6]

[^1]: This story is _On the Exactitude of Science_ by Borges. I found this version online [here](https://kwarc.info/teaching/TDM/Borges.pdf).
[^2]: When he told me this story I was flabbergasted. Rewriting an application is extremely risky, but as far as where our company is now, I actually think it was the right call.
[^3]: Freud, _Civilization and Its Discontents_, pg. 37 of my edition. [Here's another one I found](https://www.stephenhicks.org/wp-content/uploads/2015/10/FreudS-CIVILIZATION-AND-ITS-DISCONTENTS-text-final.pdf). It's in chapter 3.
[^4]: Ibid, pg. 38-39
[^5]: Ibid.
[^6]: I get that there are a myriad of reasons that we end up picking one tool over another when we tackle a problem on the job. Sometimes it's due to a legacy codebase or department mandate. I also recognize that if you are looking for a job using this or that technology it really helps to have on your resume that you handled a project with that technology. This blogpost is responding to a behavior I saw at my previous job and that I have unintentionally adopted.