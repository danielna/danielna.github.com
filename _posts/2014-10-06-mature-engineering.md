---
layout: post
title: Mature Engineering
subtitle: Reflecting back on a year on the job.
tags: text
redirect_from: "/2014/10/06/mature-engineering.html"
---

Previously <a href="/2014/03/03/man-at-work.html" title="Man at Work">I wrote some observations I had about working at Etsy when I hit the five month mark</a>. Since October 1 was my one year mark, I wanted to add to those thoughts.

## On Being a Senior Engineer

Earlier this year I read <a href="http://www.kitchensoap.com/2012/10/25/on-being-a-senior-engineer/" target="_blank">"On Being a Senior Engineer",</a> a blog post by John Allspaw, the SVP of Infrastructure and Ops at Etsy. I think the rest of this blog post is somewhat predicated on the contents of his post, mostly because after I read it it changed my perspective on the type of work I was doing, how I was doing it and why.  If you haven't read his post I suggest you do so.

But I'll preface it by saying this: that post will only resonate with you if you care about being good at your job.  And while its contents are primarily targeted towards engineers, one of the tl;dr's is that there are a lot more factors to being an effective agent of progress and change than just domain knowledge.  Emotional and social intelligence transcend industries.

So here's my tl;dr: read the post.  It's worth your time.

## Why Culture Isn't Bullshit

Well, false; sometimes culture is bullshit.  Culture is bullshit when a company thinks that having a ping pong table makes up for overbearing and demeaning management.  Culture is bullshit when "unlimited vacation" is an intentional bait-and-switch to represent "no vacation."  Culture is bullshit when misguided engineers take pleasure in forcing interview candidates to experience as uncomfortable an interview experience as possible to feed their own egos.  Perhaps a more apt wording is that in our industry, culture is _often_ bullshit.

The shared characteristic between all of these very real life scenarios is that they lack maturity and foresight.  Management often doesn't realize that when you're nice to the chief architect and mean to the intern that the rest of the company knows you're not nice people.  Management often doesn't realize that the most talented engineers are self-aware enough to understand the demand-heavy economics of the software job market while being similarly self-aware to know when they're being manipulated or swindled.  Interviewers don't realize that even smart people don't like to be bullied, and that senior level engineers are the best representation of company culture as a whole.  And assuming that interviewees stay in the industry, they talk, and reputations of companies are built (or destroyed) by egotistical and unpleasant interviewers.

I think the biggest takeaway I've had from work with regards to culture is that culture is set from the top.  The powers that be at work were once in the software trenches themselves; they know how dehabilitating burnout can be, what it's like to leave a shitty interview, and what it's like to work in an organization that develops a detached and myopic view of the world around them.  So they combat it.  They invest in real interview training.  They host management roundtables and role play to discuss various scenarios.  They provide paid time off to volunteer.

And the output is better for it.  The employees are healthier, more fulfilled, invested in the final product and stick around longer in an industry that's notorious for job hopping.

Real culture is a long term play for long term organizations.

## Technical Problems (and Their Externalities)

It's not difficult to enumerate the explicit technical skills I've acquired this year: an understanding of web performance, a deeper knowledge of JavaScript, writing an end-to-end NodeJS application, hadoop jobs, vim and the terminal, etc.  And when most people think about the value add of technical jobs these are the types of things that are easiest to consider.  Skills that can be encapsulated in bullet points on LinkedIn.

Less obvious to identify is knowledge gained relative to systems-level thinking, simply because it's much less definitive.  Here's an interesting potential interview question: how does Google Analytics work?  What are the moving parts?  A year ago I couldn't have answered this question with any level of confidence.  But now I have an idea of how client-side events can be beaconed to a server, whose logs can be parsed, placed into a data store and then cleaned/extracted/visualized to an end user.  And at each step of that process I have a legitimate mental model of how that might work. 

The latter builds on the former.  You have to know how to write JavaScript to write a client-side beacon.  But it's the latter stuff that is the most exciting and ripe with possibility.

But by far the hardest and most valuable problems I've learned from this year have even less to do with a specific technology.  Here's a killer question: how do you delete code with confidence from a web application that serves over a billion page views per month and has 200+ active developers pushing code to its repository 50+ times a day?

Off the top of my head here's a subset of what you'd have to consider:

* How do we know the code isn't reachable?
* How do we know the code isn't being used in other pages, and that those pages aren't reachable?
* What if it is being used?  Can we remove parts of it?
* When's the last time someone touched this code?
* Who do we need to give a heads up that this code will be deleted?
* What if we delete code and something breaks?  How will we track that regression and remedy it quickly?
* What's the best way to communicate the deletion and the logic behind it?  Is that communication clear enough that others trust that we've done our due diligence when it comes to identifying a solution?
* What can we create (either text or tool) to make it easier for others who have this problem in the future?

Now **that** is a super non-obvious, superficially simple but actually gnarly problem.

The hardest questions are the ones with the most externalities.  They have potentially far-reaching effects beyond the scope of your immediate concern, require clear communication and logic with other teams, and could go wrong in a number of ways.  And sometimes they're unsexy, tedious and without much glory.  But someone's gotta do it because otherwise the problem is just going to keep recurring, and that person might as well be you.

This is the juicy, learn-from-experience stuff that will truly serve you later in your career.  It's what differentiates a seasoned, mature engineer from an engineer that knows X,Y,Z technology.

Yo, I love my job.
