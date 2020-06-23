---
layout: post
title: An Open Letter to Bozhidar Batsov
description: You can never get away from context, even when you want to.
categories: software-engineering language
---

Dear Mr. Batsov,

I want to formally thank you for the creation and maintanence of your open-source project, [RuboCop](https://rubocop.org/). I have used RuboCop both professionally and privately to ensure that my ruby code meets a high standard. The value of your work and its positive effects on mine cannot be understated.

I recently [read your reasons for dismissing the suggestion to change the name of your project](https://github.com/rubocop-hq/rubocop/issues/8091#issuecomment-637963754), given the current state of affairs in the United States. I was disappointed with your response. I expected an engineer of your caliber to recognize the relationship between the concrete and the abstract, given the technical skill required to make a quality work that I use on an almost daily basis.

I tend to believe that a failure to understand stems more from ignorance than malice, and so I would like to share my perspective as an American, and why your reasons for not changing it ring hollow to me.

## There is no apolitical technology

You can't keep politics out of software because you can't keep politics out of technology. The act of creating a technology is to say something about the world. It is to observe a phenomenon, call it a problem, and propose a solution. Technology is the human response to a perceived need--a creation intended to adjust life for oneself or another.[^1]

Politics is the branch of philosophy that seeks to answer the question "how do we organize ourselves." Technology that responds to that question in any way, shape, or form will be political. The fact that you made what is essentially a ruby linter tells me that you have a perspective on how a codebase needs to operate--how people's contributions to a codebase need to be evaluated, enforced, and organized. In other words, you made something that says something about how people need to organize themselves. How is that not political?

## The issue is not misguided individuals

Failures of the police in the United States does not come from "a few misguided individuals." It comes from a centuries-long legacy to enforce white supremacy on a systemic level.[^2] The police in the United States have their roots in fugitive slave patrols. When a slave escaped, it was a proto-police force that would go and find that person, beat them into submission, and return them to the person who legally owned them. The police have always been the protectors and servers of white law and white interest against non-white persons in the United States.

Every time a police officer murders a person of color in the United States, lots of people respond by saying "it's a few bad apples." The problem with that statement is that it is used to avoid the need to change. Why are there bad apples there in the first place, and why aren't we doing anything to remove them? If a tree consistently spits out "a few bad apples" who are bad enough to kill their fellow Americans, then it's time to look at the apple tree and see if it's corrupted, even if plenty of apples come out of it just fine.

The issue isn't that there are "a few bad apples." The issue is that these bad apples are consistently going out and killing people, and nothing is being done to stop them from doing that.

## Living under a dictator is irrelevant

The decision to name the project RuboCop has linked it to American policing, regardless of who you are or where you're from. The history of the police force in your nation is probably wildly different from mine, but that's not what you named your project after: you named it after a cheesy action movie about American police.

What that does mean is that you are disconnected from what is currently happening in the United States. That being the case, I do suggest that you read up on the origins and history of racial violence in the United States so you can understand why you were embroiled in such drama at this time.

## The hardest things to do are worth doing

Your last reason is that changing a name--especially a pretty big one like RuboCop--is hard. And yeah, it's hard. I'm not going to deny that.

You know what else is hard? Farming. I'm glad people do it though, because if people weren't farming, I wouldn't be eating.

Writing quality software is also hard. I'm glad people do it though, because if they didn't, I wouldn't be writing this in Sublime 3 text editor, using git to save it and jekyll to serve it on top of GitHub's totally free service. It's thanks to the hard work that those people have done that we're even able to have this conversation at all.

The difficulty of a task is not a valid reason to avoid it, particularly when it may be the right thing to do.

## None of this makes you a bad person

It makes you a normal person. Normal people like movies like Robocop. Normal people are totally unaware of the nuances of places outside of their own cultural context. Normal people come up with names for things that mean things they don't intend. I don't hold you responsible for doing anything more than making a valuable tool and misunderstanding a culture and situation far removed from yourself.

All I'm asking of you is to engage with the fact that you are human, that you do make mistakes, and what you intended to be a light-hearted reference to a cheesy action movie may hold a whole lot more baggage than you bargained for.

## Should you change the name of the project?

I don't know. It's not my project, so it's not my decision. That decision lies solely with you and your team.

What I do hope to see from you is a renewed interest in examining the situation in the United States and evaluating that situation's relationship to your project. Read and watch what I shared, and then rewatch the Robocop series. You may find nothing, or you may discover that the process of naming your project after that film says something you didn't want it to say.

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

[^1]: I was first introduced to the idea that every invention is political through the book [*Amusing Ourselves to Death* by Neil Postman](https://www.amazon.com/Amusing-Ourselves-Death-Discourse-Business/dp/014303653X/ref=sr_1_1?dchild=1&keywords=Amusing+Ourselves+to+Death&qid=1592501160&sr=8-1&tag=duc0c-20). It was a stellar examination of the effect of a medium on a message, how the same message in a different medium causes people to think and reason about the world differently, and how technological advances bring both benefits and drawbacks. It convinced me to rely more heavily on the written word than television to understand things. If I were in charge, I would make it required reading in the United States.
[^2]: One of the folks on that GitHub thread shared [this link](https://crimethinc.com/2017/03/15/slave-patrols-and-civil-servants-a-history-of-policing-in-two-modes) that makes this point clear. I also suggest watching [Last Week Tonight with John Oliver](https://www.youtube.com/watch?v=Wf4cea5oObY) for more information. I also found the explanation of origins and history of slavery in the United States in Harari's book [*Sapiens*](https://www.amazon.com/Sapiens-Humankind-Yuval-Noah-Harari/dp/0062316117/ref=sr_1_1?dchild=1&keywords=Sapiens&qid=1592500026&sr=8-1&tag=duc0c-20) extremely enlightening, on top of the whole book itself. [This is the relevant excerpt from that book](https://www.dancollinsandapiano.com/purity-in-america).
