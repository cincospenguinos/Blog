---
layout: post
title: An Open Letter to Bozhidar Batsov
description: You can never get away from context, even when you want to.
categories: software-engineering language
date: 2020-06-27 10:37 -0600
---
Dear Mr. Batsov,

I want to formally thank you for the creation and maintenence of your open-source project, [RuboCop](https://rubocop.org/). I have used RuboCop both professionally and privately to ensure that my ruby code meets a high standard. The value of your work and its positive effects on mine cannot be understated.

I recently [read your reasons for dismissing the suggestion to change the name of your project](https://github.com/rubocop-hq/rubocop/issues/8091#issuecomment-637963754), given the current state of affairs in the United States. I was disappointed with that response. The response felt malinformed and indifferent to the American situation to me, and reflected a misunderstanding about technology and meaning in general.[^1]

I tend to believe that a failure to understand stems more from ignorance than malice, and so I would like to share my perspective, both as an American and as a colleague.

## There is no apolitical technology

It is impossible to keep politics out of software because it is impossible to keep politics out of technology. The act of creating a technology is to say something about the world. It is to observe a phenomenon, call it a problem, and propose a solution. Technology is the human response to a perceived need--a creation intended to adjust life for oneself or another.[^2]

Politics is the branch of philosophy that seeks to answer the need of human organization. Technology that responds to that question in any way, shape, or form will be political. The fact that RuboCop is a ruby linter tells me that it has a perspective on how a codebase needs to operate--how people's contributions to a codebase need to be evaluated, enforced, and organized. In other words, RuboCop says something about how people need to organize themselves. How is that not political?

## The issue is not misguided individuals

Failures of the police in the United States do not come from "a few misguided individuals." It comes from a centuries-long legacy to enforce white supremacy on a systemic level.[^3] The police in the United States have their roots in fugitive slave patrols. When a slave escaped, it was this proto-police force that would go and find that person, beat them into submission, and return them to the person who legally owned them. The police have always been the protectors and servers of white law and white interest against non-white persons in the United States.

Every time a police officer murders a person of color in the United States, lots of people respond by saying "it's a few bad apples." The problem with that statement is that it is used to avoid the need to change. Why are there bad apples there in the first place, and why aren't we doing anything to remove them? If a tree consistently spits out "a few bad apples" who are bad enough to kill their fellow Americans, then it's time to look at who's picking the apples and why they keep picking bad ones.

The issue isn't that there are "a few bad apples." The issue is that these bad apples are consistently going out and killing people, and nothing is being done to stop them from doing that.

## Living under a dictator is irrelevant

You mentioned that your home country of Bulgaria has a different organization than the United States, and that the police force in your country is different from mine in various ways. All of this I trust to be true.

This statement isn't relevant to RuboCop. It's irrelevant because RuboCop is named after an American film about American police.

The moment the project was named RuboCop was the moment that the project inherited the context of that American film and, by extension, the traditions of the American police force. The fact that you're from Bulgaria is irrelevant to the project because the project is named after an American cultural artifact.

## The hardest things to do are worth doing

The last listed reason for not changing the name of the project is that it is hard to do. And yeah, it's hard. I'm not going to deny that.

You know what else is hard? Farming. I'm glad people do it though, because if people weren't farming, I wouldn't be eating.

Writing quality software is also hard. I'm glad people do it though, because if they didn't, I wouldn't be writing this in Sublime 3 text editor, using Git to save it and Jekyll to serve it on top of GitHub's totally free service. It's thanks to the hard work that those people have done that we're even able to have this conversation at all.

The difficulty of a task is not a valid reason to avoid it, particularly when it may be the right thing to do.

## None of this makes you a bad person

It makes you a normal person. Normal people like movies like Robocop. Normal people are totally unaware of the nuances of places outside of their own cultural context. Normal people come up with names for things that mean things they don't intend. I don't hold you responsible for doing anything more than making a valuable tool and misunderstanding a situation far removed from yourself.

What I'm asking from you is what I ask from everyone: to be willing to reevaluate oneself and one's outlook on things, to consider the ways the things we make impact people, and consider the power of language and technology, its meaning, and its purpose. I think everyone working in tech needs to examine and reexamine what it is they are making and what metaphors they are using to describe it. It is that lack of curiosity and that lack of personal responsibility that created the now ubiquitous metaphor of [master and slave](https://en.wikipedia.org/wiki/Master/slave_(technology)).

## Should you change the name of the project?

I don't know. It's not my project, so it's not my decision. That decision lies solely with you and your team.

What I do hope to see is a renewed interest in examining the situation in the United States and evaluating that situation's relationship to your project. Read and watch what I shared, and then rewatch the Robocop series. You may find nothing, or you may discover that something you made and named says something you did not intend it to say.

<style>
	.signature {
		display: flex;
		flex-direction: column;
		text-align: right;
	}

	.signature > * {
		margin: 4px 0;
	}

	.job-title {
		font-size: smaller;
	}
</style>

<div class="signature">
	<span>Sincerely,</span>
	<span>Andre LaFleur</span>
	<span class="job-title">Software Engineer and rando on the internet</span>
</div>

[^1]: I wrote this before I saw [Bozhidar's response to the vitriol](https://github.com/rubocop-hq/rubocop/issues/8091#issuecomment-640158172) [and his subsequent blog post on the subject](https://metaredux.com/posts/2020/06/08/the-rubocop-name-drama-redux.html). I initially wrote this with him in mind, but after a few days of reflection I realized he's not my audience. My audience is everyone else who would voice a similar perspective to his initial one--the kind of perspective that folks in my earlier level CS classes in college would have repeated. I have nothing against him--again, I'm fond of the work he's done--and I do not support the belligerent people who harassed him for naming his project after Robocop. So Bozhidar, if you're reading this, thank you again for your work and I'm sorry the situation in the US splashed onto you in a negative way. This letter isn't a callout; it's an opportunity to share an interdisciplinary approach to software and highlight the power of names and metaphors. I'm simply using your initial response as a way to respond to what I believe are misunderstandings that continue to pervade computing. To everyone else: please peruse [Tim Riley's post on the subject as well](https://timriley.info/writing/2020/06/08/rubyists-we-must-do-better/), as his statement on the whole debacle mirrors my own thoughts and feelings.
[^2]: I was first introduced to the idea that every invention is political through the book [*Amusing Ourselves to Death* by Neil Postman](https://www.amazon.com/Amusing-Ourselves-Death-Discourse-Business/dp/014303653X/ref=sr_1_1?dchild=1&keywords=Amusing+Ourselves+to+Death&qid=1592501160&sr=8-1&tag=duc0c-20). It was a stellar examination of the effect of a medium on a message, how the same message in a different medium causes people to think and reason about the world differently, and how technological advances bring both benefits and drawbacks. It convinced me to rely more heavily on the written word than television to understand things. If I were in charge, I would make it required reading in the United States.
[^3]: One of the folks on that GitHub thread shared [this link](https://crimethinc.com/2017/03/15/slave-patrols-and-civil-servants-a-history-of-policing-in-two-modes) that makes this point clear. I also suggest watching [Last Week Tonight with John Oliver](https://www.youtube.com/watch?v=Wf4cea5oObY) for more information. I also found the explanation of origins and history of slavery in the United States in Harari's book [*Sapiens*](https://www.amazon.com/Sapiens-Humankind-Yuval-Noah-Harari/dp/0062316117/ref=sr_1_1?dchild=1&keywords=Sapiens&qid=1592500026&sr=8-1&tag=duc0c-20) enlightening. [This is the relevant excerpt from that book](https://www.dancollinsandapiano.com/purity-in-america).
