---
layout: post
title: Man at Work
subtitle: Observations on the road to five months at Etsy.
tags: text
---

I started my new job as a software engineer at <a href="http://www.etsy.com">Etsy</a> on October 1, so as of the writing of this post it's been about five months.  I haven't written about career-related things since Hacker School, so for posterity's sake let's recap the road to here.

## Interviewing

Being unemployed for 5-6 months while financially independent was generally fine with the proper foresight and planning, but towards the latter part of Hacker School I was _really_ thinking about jobs.  Paying for COBRA was also getting very old, very fast.  Consequently I took a lot of interviews in a very short time period.

Startup tech interviews are somewhat unique from other industries in that they're commonly multi-stage affairs.  Typically the first step is to talk to an HR representative about the position/company in general and to schedule a phone screen with an engineer.  The phone screen with the engineer is usually short, on the scale of 30 mins, but can be as involved as coding over a shared text editor or as simple as a verbal Q&A.  A lot of companies then include a "take-home assignment" which is completed over the course of X days and returned via email.  Assuming you get past those stages you're then invited to interview on-site with 3-5 employees in a row, 45min - 60min each.  Behavioral questions, technical questions, white-boarding; it's all fair game.  Companies either give you a decision after the on-site or can even call you back for a second in-person meet, this time with executives who have the final say on your hire.

I think at one point I scheduled seven interviews of some sort (phone/in-person/skype) in a five day period.

Hard-earned advice: don't schedule seven interviews in a five day period.

Interviewing was really, really exhausting.  It's a combination of factors -- the prep work, the context switching, the stress of being mentally "on" at all times -- and it wears on you.  I was serious about finding a good job as quickly as I could but after that week I went back home to DC to physically recharge before continuing any of the interviews.  I was burned out.

So even beyond the subject matter expertise of interviewing, the practical aspects of interviewing are trying.  But despite the fatigue, as someone who's never run a gauntlet of tech interviews before I found it really enlightening.  You can tell a lot about a company's culture in how they conduct their interviews.

Things to evaluate:

* **Simple - the interviewer**: Likely someone higher up in the engineering/management team.  If they're an unpleasant person you're unlikely to escape working with them.  And in every job I've ever had the most senior employees are the best microcosm for company culture as a whole.
* **Simple - the technical questions**: You'll know if you're swimming too shallow or in too deep depending on how difficult the questions are.  Meaning you'll typically know if you'll be bored at this company or in way over your head.
* **Harder - the meta aspects of the technical questions**: Some of the worst interviews I had were just a [succession of JavaScript gotcha's](http://blog.codacy.com/short-guide-js-gotchas/). <a href="#footnotes">[1]</a>  Like, literally the content of this link, one after the other.  That isn't to say these questions aren't _fair_, because they evaluate real domain knowledge and you should know this stuff.  But gotcha's in isolation are a horribly lazy way to evaluate someone's ability to perform on a day-to-day basis, in addition to making it seem like the point of the interview is to stump the candidate.
* **Hardest - the meta aspects of the interview overall**: The most perplexing thing about the tech industry is that a lot of companies complain about a "lack of good workers" but then decide to randomly throw unprepared/disinterested/busy engineers into interviews without having a cohesive strategy on how to evaluate their candidates.  Here's an absolute truth: just because someone can pass a technical screen does not in any way make them qualified to give one.  The best companies bring in interviewers with different perspectives, not only to gain a holistic perspective on the candidate but to offer a holisitic perspective of the company.  Instead of leaving the interview bitter because the questions were irrelevant, leaving a cohesive interview can create the sentiment that even if you don't get it, at least it was fair.  The questions were in bounds given the job description and your resume.  You'd still recommend interviewing at that company to a friend and there are no hard feelings.

I had a few really positive interviewing experiences and they left a mark on how I'll evaluate/conduct interviewing moving forward.  Etsy absolutely nailed all of these points.  Only upon becoming an employee did I learn that it's because they take hiring very, very seriously and devote the time/resources to it in kind.

## Work

Etsy is a [well-oiled, tech-centric machine](http://codeascraft.com/).  I have never worked anywhere with such sophisticated engineering processes, perhaps the most mind-blowing of which remains [continuous deployment](http://www.slideshare.net/beamrider9/continuous-deployment-at-etsy-a-tale-of-two-approaches). <a href="#footnotes">[2]</a> I've also never worked on an engineering team even remotely this large (~150 and growing?!) with everyone working at a high level.

Five months of observations:

* There's a strong focus on building tools in-house to streamline common tasks and it's a big win.  Not only does it make everyones job easier but it facilitates a maker culture that is consistent with Etsy the product. <a href="#footnotes">[3]</a> 
* Etsy is proactive about combating the less desirable aspects of the tech industry: [sexism](http://www.etsy.com/hacker-grants), [reckless consumption](http://www.etsy.com/blog/news/2012/etsy-joins-the-b-corporation-movement/), and [assholes](http://www.slideshare.net/chaddickerson/code-as-craft-building-a-strong-engineering-culture-at-etsy). They're also public about it. It has an undeniable effect on the type of people who are attracted to and succeed within the company.
* It's possible to have remote employees and actually treat them like employees, but it's a company-wide effort that everyone must buy into both mentally and procedurally.  But once it works it's a major, major asset.
* There are a lot of different teams and a lot of cross-pollination in tasks within engineering.  That's exciting because it provides the opportunity to learn about technologies in which you have no experience.  For example, the bulk of my time so far has been writing [scalding jobs on the hadoop/bigdata stack](https://speakerdeck.com/mcfunley/scalding-at-etsy) to generate analytics around user behavior on mobile.  Six months ago I couldn't have even told you what hadoop or a funnel was.
* The Etsy onboarding process was _great_. By far the best I've had. I sat with 4-5 different teams for 1-2 weeks each, which not only allowed me to meet people across the company but also provided the opportunity to get acquainted with the different tech stacks in a hands-on way. It's super gutsy and expensive to have that long of an onboarding process for new employees.  It's definitely a long-term play.
* Having a dog come up to you for a belly rub first thing in the morning is the best possible way to start the workday.  Office dogs need to be a thing everywhere.

But the most important thing about Etsy is that everyone actively cares and celebrates getting better at what they do.  I have enough work experience to know how much of a difference that mentality makes when it comes to career and personal growth.  Productivity and apathy are similarly contagious.  Standards of excellence are best enforced when they're culturally enforced.

It's not _just a job_; it's code as craft.

<h3><a name="footnotes"></a>Footnotes</h3>

[1] I had actually studied the contents of this exact link and still brain-farted on some of them.

[2] All engineers can push code to production multiple times a day.  And by multiple times I mean every 5 minutes if you want to, as production pushes are automated.  Say goodbye to "deployment Thursday" or waiting on free cycles from an overworked and disgruntled SysAdmin.

[3] It takes guts for a company to devote time to home-grown devtools.  Granted Etsy's success and maturity as a product lend itself to engineers having the time for internal projects, the celebration of internal tools is undoubtably a byproduct of cultural intention.
