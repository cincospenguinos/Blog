---
layout: post
title: Building an Application From Scratch
description: I made a thing! I learned a lot! I want to share that with you!
categories: software-engineering
---

I recently released the first version of a [simple motivation app for hobbyist writers](https://www.keepwriting.io). It was not my idea to build it (more on that in a minute) but I was the entire engineering department for the project. I designed it and wrote it all by myself. I'm quite proud of it!

I realized that some folks may not know how to get started with something like this, and I wanted to share my experience and advice on how to get something like this built. This post is about exactly that.

## How it started

A buddy of mine reached out to me way back in October telling me about an app idea he had. I'm generally skeptical of friends and family members who have app ideas, as I've heared a bajillion of them and usually they come down to "make me a thing that will make me money; I'll pay you nothing to do it." I typically let people at least talk about their ideas with me though, just in case one of them has potential.

This time was a little different.

"I've been using this mobile app to help me work out," my buddy said. "I get charged for every day I don't work out."

"Charged?" I asked. "You mean like money?"

"Yup. I lose money if I don't work out a day."

"And it works? You get up and move around?"

"Yeah! There's a decent bit of science behind it. Threats of punishment tend to change behavior more than promise of rewards. Hence I workout everyday. I just want that, but for writing a novel."

"What do you mean?"

"Every time I don't write enough words on my manuscript, I want to get charged a fee. The punishment of not writing would be greater than the work required to simply write."

Weighing the idea, I decided to accept it, with one caveat. Initially my business partner wanted to make a mobile app. I could do that (I've built one and released it before,) but the folks who would use this app would probably be on a desktop or laptop, writing in a word processor. A mobile app wouldn't reach our audience quite like what we want. I suggested a web application instead, as that's both what our target audience would access more easily and a web app matches my skillset.

We agreed on a date and time to sit down and discuss all the details. The main things we needed to has out were

* Ownership of the application and business
* What the product needed to do
* How we would go about building the application

## What we did

What I did:

* I employed XP as closely as I could with my business partner
	* This required training on his part
	* Training required a bit of patience on my part--periodically I would build up a huge number of stories that needed his approval over weeks, messing with our velocity
	* Ultimately though XP was a good framework to get things moving quickly, efficiently, and pleasantly
* I test-drove the entire thing
	* No production code unless there was a test around it (with a couple of exceptions)
* My business partner and I incepted ever feature and discussed/debated each benefit
	* I treated my business partner like an on-site customer (see Shore's book)
	* We met twice a week for 20-60 minutes, discussing what we did, what we were going to do, and what we wanted to have happen in the next few weeks
	* Our first step was compiling a list of things we wanted the app to do
	* We then cut every feature that wasn't absolutely critical to the product
		* Things we initially cut: resetting passwords, snoozing projects, an admin/support panel
		* We honed in on the smallest little pieces that were absolutely mandatory to our application, and built those
	* This allowed us to have the main product for ourselves in about a month or two of work
	* We used ourselves as our first testers, finding and stomping out bugs
* We met twice a week for 20-60 minutes to discuss what was happening that week
	* My business partner handled all of the business things (enrolling with the government, getting a business license, etc.)
	* I focused solely on building the product, relying on him as customer
	* He would QA the stories I wrote, report bugs to me, etc.
	* We would go over our tracker
* In case you are wondering what tools I used:
	* Ruby 2.7.1
	* Rails 6.0
	* Heroku
	* PostgreSQL
	* Namecheap for domain
	* CircleCI for continuous integration
	* Pivotal Tracker to manage the work
	* Google Workspaces when we needed an email address
	* Local credit union that offered free online banking for businesses
	* Stripe for managing payments
	* Windows Subsystem Linux for development
	* Git + GitHub for version control
	* Sublime Text 3 for a text editor
	* Rbenv to manage my ruby versions

What I learned:

* Having a customer on hand to check everything you're doing is amazing
	* My business partner knew what he needed and I was able to avoid making something nobody wanted by incorporating him early and often
* Taking the time to write stories helps you organize your work and collaborate with someone else
	* Writing stories communicates what needs to happen
	* Writing stories helps break the work down into little pieces for yourself
	* Writing stories ensures your customers get something valuable each go around
* TDD from the start allows massive restructuring of an application
	* My test suite saved me from introducing a number of bugs during refactoring
	* My test suite allowed me to perform huge refactors on my codebase with confidence
	* My test suite is only good when it's good though--take care of your test code!
* CI is good to have, except when it isn't good
	* I had to fight a lot with CircleCI
	* It wasn't terribly necessary when it was just me--when it broke I found myself ensuring my tests worked locally and then deploying manually
	* Part of this is on me (I don't know how to use CircleCI as well as other folks do)
	* Failing tests that don't actually fail makes CI noisy and worthless--take care that your suite doesn't barf for no good reason
* Rails lets you get away with some bad patterns
	* Bucket of models, bucket of views, bucket of controllers grows really, really quickly
	* Model coupling leads to shotgut surgery when a model changes
	* Bloated controller tests for business logic makes things slow
	* Breaking things out into services and presenters makes things a lot cleaner and easier to test
* React isn't a silver bullet
	* Some things needed to be on the frontend, and that added complexity
	* React allowed sleek user interactions and reusable patterns, but required extra code to do things
	* Some problems were better solved with rails forms than React ones
* Bugs are inevitable. Suffering them is optional
	* Every time you find a bug, write a test that exposes it, and then green the test up
	* If you have a few bugs that propogate after fixing them, build out a solution for them
	* The time zone issues were solved by test-driving an object that standardized a solution for it
* YAGNI isn't just for code
	* There are so many features, so many things that were not necessary to build the thing
	* Finding what is essential and building that and only that allowed us to move extremely quickly

What had gone well:

* Fronting the cost of starting was wise
	* My business partner and I made a very small investment each and it will last us months in terms of operating costs
	* We won't have to 
* Refactor early, refactor often
	* What makes software soft is its ability to change it. If you're not changing it often without breaking it, you aren't keeping it soft
* Get it working, then make it clean, then make it performant if needed

What I would have done differently:

* Tried the application with my buddy from the get-go
	* Have me charge him and keep up with him via email
	* Have him write back to me via email in order to submit his words
	* This would have allowed us to test the idea quickly and efficiently
	* We would not be in the awkward stage we are in right now if we had done that from the get-go
* I would have expected burnout
	* I was pretty sick of code just before the release--I was doing this in my spare time while pulling a day job doing the same thing
	* Take some time away from computing--read a book, go outside, drink a few beers, play some games, hang out with friends. Have a life outside of work
