---
layout: post
title: Different Code for Different Folks
description: Context matters, I guess
categories: software-engineering
date: 2021-02-04 12:25 -0700
---
I received a bit of feedback from a [previous blog post I wrote about code comments](http://cincospenguinos.github.com/blog/software-engineering/2020/06/03/on-code-comments.html). The crux of the feedback was that lots of engineers have different perspectives on code comments, and so take what any one of us say about the subject with a grain of salt. There's a petty part of me that wants to write off that response, but upon reflection I realized something about my previous statement about comments: it assumes we're discussing code for an application that will need to be changed by multiple people[^1]. And that's not the only reason code exists.

Looking back on my own career, I can think of a few reasons to I wrote code:

1. To learn a new technology, algorithm, or language
1. To teach a programming principle to somebody else
1. To build an application for myself or somebody else

I think each of these reasons for code to exist can be a litmus test for whether or not to write a code comment. If you're just barely starting programming and you're not used to reading code, comments from yourself or your instructor can be helpful, like training wheels for a new cyclist. If you're learning a new language--[especially one with a totally different paradigm than what you've messed with before](https://elixir-lang.org/)--comments can be helpful. The same can be said about a new algorithm that you're putting together or implementing.

I still believe what I wrote before though--computer code exists to communicate to people just as much as it exists to make a machine perform computational work. If there's ever a chance that you will need to share that code with others (or even yourself in the future) doing the work to make your code readable pays off in dividends[^2]. The extra care and work is good for the code, for future maintainers, and for you.

All of that being said, if you [work for me](http://keepwriting.io) and check in commented out code, I will probably fire you. My business's survival depends on the quality of its code base, as do many other SaaS companies, and my code base needs to be easy to change. That can only happen when it's clean.

[^1]: I thought that was obvious by the stupid meme at the top of the post, but maybe folks didn't pick that up from context.
[^2]: My last big project for my Bachelors required us all shifting seats, where I went from putting together [the integration of our ML system](https://github.com/cincospenguinos/ScamProtectorsMonitor) to our database to [working on the backend](https://github.com/cincospenguinos/ScamProtectorsWeb). If I had not taken care to make the code for that integration plain and readable, my colleagues would have had a terrible time getting that portion of our application up to spec, and we would have missed our deadline.