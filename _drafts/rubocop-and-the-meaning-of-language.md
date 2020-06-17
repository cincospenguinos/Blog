---
layout: post
title: An Open Letter to Bozhidar Batsov
description: You can never get away from context, even when you want to.
categories: software-engineering language
---

Dear Mr. Batsov,

I want to formally thank you for the creation and maintanence of your open-source project, [RuboCop](). I have used RuboCop both professionally and privately to ensure that my ruby code meets a high standard, particularly when collaborating with others. The value of your work and its positive effects on mine cannot be understated.

I recently [read your reasons for dismissing the suggestion to change the name of your project](https://github.com/rubocop-hq/rubocop/issues/8091#issuecomment-637963754), given the current state of affairs in the United States and the greater recognition of systemic racism. I was disappointed. I expected an engineer of your caliber to recognize the relationship between the concrete and the abstract, given the technical skill required to make a quality work that I use on an almost daily basis.

I tend to believe that a failure to understand stems more from ignorance than malice, and so I would like to suggest to you why changing RuboCop's name would be a wise decision, and why your reasons for not changing it ring hollow.

## There is no apolitical technology

You can't keep politics out of software because you can't keep politics out of technology. The act of creating a technology is to say something about the world. It is to observe a phenomenon in the world, call it a problem, and propose a solution. Technology is the human response to a perceived need--a creation intended to adjust life for oneself or another.

Politics is the branch of philosophy that seeks to answer the question "how do we organize ourselves." Technology that responds to that question in any way, shape, or form will be political in one way or another. The fact that you made what is essentially a ruby linter tells me that you have a perspective on how a codebase needs to operate, and so you created a solution to that problem. That was a political act, and every decision you make with that project is a political act as well.

Look carefully at how RuboCop operates. It makes assertions on code style, and would fail a build if it finds any infractions on that style. It is to be used as an enforcer of code, and it is used by maintainers of other projects to exclude code that fails to meet certain laws that it asserts. That, in and of itself, is making a statement on how people need to be organized when it comes to a code base. How is that not political?

The assertion to "keep politics out of software" is virtually identical to the mainstream gamer assertion [that games should not be political](). That statement is inherently politically charged. It really means "games should not have political outlooks that aren't mine," and in your case your statement sounds more like "software should not have politics that I find acceptable."

## It is not misguided individuals

Failures of the police in the United States does not come from "a few misguided individuals." It comes from a centuries-long legacy to enforce white supremacy on a systemic level[^1]. The police in the United States have their roots in fugitive slave patrols and anti-union efforts. When a slave escaped, it was a proto-police force that would go and find that person, beat them into submission, and return them to the person who legally owned them. The police have always been the protectors and servers of white law and white interest against non-white persons in the United States.

Every time a police officer murders a person of color in the United States, lots of people respond by saying "it's a few bad apples." The problem with that statement is that it is used to avoid the need to change. Why are there bad apples there in the first place, and why aren't we doing anything to remove them? If a tree consistently spits out "a few bad apples" who are bad enough to kill their fellow Americans, then it's time to look at the apple tree and see if there's something wrong with it.

## Living under a dictator is irrelevant

Imagine that I made a validation library for an ORM of some sort. Imagine that it was pleasant to use, easy to configure, and as simple to include in your project as throwing its name in your Gemfile. Would you like it if I named it after one of the ugliest parts of your nation's history, or related it in some way to faults of your nation's systems? You can think of names better than I can, and I would not dare belittle another man by naming something after one of the worst parts of another's culture and heritage.

Your statement that "the police are kind of okay in my dictatorship" is irrelevant, because your name is based off of an American film about American issues with American police, all of which have American faults. Sure, you're cool with living under a dictator, but that doesn't mean that your project's name lives outside of its relationship to American police. It doesn't work that way because homie, *you named your project after a movie about American policing*. You decided to associate your project with a goofy fictionalized American police force. You brought that context onto your own project by naming it what you named it.

## The hardest things to do are worth doing

Your last reason is that changing a name--especially a pretty big one like RuboCop--is hard. And yeah, it's hard. I'm not going to deny that.

You know what else is hard? Farming. I'm glad people do it though, because if people weren't farming, I wouldn't be eating.

Writing quality software is also hard. I'm glad people do it though, because if they didn't, I wouldn't be writing this in Sublime 3 text editor, using git to save it and jekyll to serve it on top of GitHub's totally free service. It's thanks to the hard work that those people have done that we're even able to have this conversation at all.

The difficulty of a task is not a reason to avoid it, unless you are including the benefits. And even then, the benefits of renaming RuboCop are significant: your project would not have the association with a tone-deaf action film that glorifies a force that has long been used for the oppression of other people. You may love the film Robocop, but are you sure that you want your name and personhood connected to such a thing?

## None of this makes you a bad person

It makes you a normal person. Normal people like movies like Robocop. Normal people come up with names for things that mean things they don't intend. I don't hold you responsible for doing anything more than making a valuable tool and misunderstanding a culture and situation wildly removed from yourself.

All I'm asking of you is to engage with the fact that you are human, that you do make mistakes, and what you intended to be a light-hearted reference to a cheesy action movie holds a whole lot more baggage than you bargained for. Just as I won't be making tool that uses Bulgarian Nationalism as a metaphor, I hope you would reconsider your stance and be willing to look into renaming the project that isn't connected to something you wouldn't want to be associated with.

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

[^1]: One of the folks on that GitHub thread shared [this link](https://crimethinc.com/2017/03/15/slave-patrols-and-civil-servants-a-history-of-policing-in-two-modes) that makes this point clear. I also suggest watching [Last Week Tonight with John Oliver](https://www.youtube.com/watch?v=Wf4cea5oObY) for more information.

Dear Mr. Batsov,

I want to formally thank you for the creation and maintanence of your open-source project, [RuboCop](). RuboCop has made the development and maintanence of a variety of projects belonging to me and my employer ensure a firm linting standard of ruby. The long-standing effects on those codebases cannot be understated.

I recently read throug the [GitHub issue encouraging you to change the name of the project](https://github.com/rubocop-hq/rubocop/issues/8091), and like you, I was disappointed by how vitriolic the whole conversation became. Generally I've found the Ruby community to be collaborative and helpful, reflecting the fun, enjoyable experience of programming in Ruby. I also read [your post on the subject](https://metaredux.com/posts/2020/06/08/the-rubocop-name-drama-redux.html), wherein you outline how challenging it is to maintain an open-source project and how frustrating it can be to be in the center of drama that you are otherwise not connected to or not involved in. You certainly have my support when it comes to overseeing and maintaining RuboCop.

I observed that you made some statements in that issues thread that I felt reflected a misunderstanding about technology and the world at large. I don't blame you for making those statements--as a matter of fact, I heard similar statements made by malinformed Computer Science students all throughout my time at college. My goal with this letter is to explain why I found some of your statements misinformed, why the things do may not intend harm but still can *do* harm, and why I think changing the project's name would be wise.

I'll mostly be focusing on [your statement in the issue itself](https://github.com/rubocop-hq/rubocop/issues/8091#issuecomment-637963754), as I believe it reflects a misunderstanding of the situation in the United States and a misunderstanding about language, context, and meaning.

## There is no such thing as an "apolitical invention"

Every time someone invents a new piece of technology, they are saying something about the world. They are saying that they observe a problem and they are proposing a solution to that problem. The creator of an invention is admitting that they see a problem in the world simply by virtue of them making a solution to that problem.

A great example is the invention of the second as a unit of measurement of time. Before the idea  people felt just fine not dividing up time into separate measurements, and now hours, minutes, and seconds are so ubiquitous that the invention isn't questioned. It's only after visiting another country with a wildly different interpretation of the invention of keeping time that I observed that it was an invention at all.

The act of naming something is an inherently political act as well. Naming something in software is to apply a metaphor to an abstract concept for the purpose of understanding it.

To attempt to "keep politics out of software" is to attempt to keep hydrogen atoms out of water molecules--you can't. That's not how things work. Things mean things. Things mean things even when you didn't intend for them to mean things. Things mean things even when they aren't the things you *intended* them to mean. It's part of inhereting the world-wide context of language, history, and culture. You didn't ask to be part of a context, sure, but that doesn't mean you don't belong to one.

## Put yourself in our shoes

Imagine I made a fancy model validation library for an ORM. Imagine it works seamlessly, 

## So you lost your cool

We all do, periodically. It's only human to feel frustration when people who have no idea who you are, what you're about, and why you're doing what you're doing roll in and bark at you for making a decision and sticking with it.

## I won't be holding you accountable

RuboCop is your project. You're the one who made it. You're the one who's doing the work. I think it would be unfair for me to demand that you adjust your project simply because I said so.

That said, how we name things and how we talk about things gives implicit messages about who is and is not accepted. As I've shared this blog with other people I've consistently been given the feedback that my language is often too gendered--I tend to refer to engineers using masculine pronouns. This isn't intentional on my part--I'm a dude, and so when I imagine others I tend to imagine dudes. The language I tend to use reflects that implicit bias, and the effect of that bias is that it excludes women or non-binary persons from being recognized.

"Keep politics out of tech" is as helpful as "keep thinking out of making" and as possible to do as "keep hydrogen atoms out of water molecules."

Sources:

* This is the author's post: https://metaredux.com/posts/2020/06/08/the-rubocop-name-drama-redux.html
* This is the GitHub discussion: https://github.com/rubocop-hq/rubocop/issues/8091
* Amusing Ourselves to Death by Neil Postman
* There's only two genders: male and "political"