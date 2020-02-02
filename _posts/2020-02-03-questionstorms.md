---
layout: post
title: Questionstorms
subtitle: When you have no idea where to even start, ask more questions.
tags: text
---

Sometimes at work I'll encounter a problem that I have no idea how to scope. I'm
not referring to "what technologies should we use to build this thing" or "how should
we break this project into tickets," but rather "what are we even supposed to build here?"
We'll have an end state in mind - "our product needs to be able to do X" - but
the precise requirements of the ask are unknown, and there are so many stakeholders
to consider that it feels like venturing immediately into discussions around
code is doomed to spinning our tires. When this happens I like to host a Questionstorm.

A Questionstorm is a meeting format where attendees are only allowed to
ask questions. The goal of a Questionstorm is to "[map the potato](http://www.moishelettvin.com/2016/02/23/i-dont-know/)"
of a problem, which is a phrase I picked up at Etsy which refers to exploring
the edges of a poorly defined problem space. Performing a series of Questionstorms
with the stakeholders who are most important to the outcomes of your problem is a great
way to know what concerns are top of mind for those groups, which in turn can help
direct your future requirements gathering.

---

## The focus is questions

The most important characteristic of a Questionstorm is that the focus is on asking
questions. Let me repeat that: **the focus is on asking questions**. Answers are
not a goal for this meeting.

That's initially uncomfortable for many people, as I often find that those new to
the Questionstorm format try to interject with answers ("This will be quick, but...").
Don't let that happen. The focus on questions is important for a few key reasons:

* Answers, especially to "obvious" questions, negatively impact the
psychological safety of asking more questions. People become hesitant to ask "obvious"
questions, which means they're thinking too hard about the merit of their questions
instead of asking questions.
* Answers take time to express and invite more discussion, both of which take
time away from asking more questions.
* Answers are easy to fill in afterwards.

In my best [Tyler Durden](https://www.imdb.com/title/tt0137523/) impression: the
only question of Questionstorms is "what's the next question?"

## How to run a Questionstorm

First, identify the initial topic and a meeting proctor.

A proctor's responsibilities are short but important:

1. Don't let people give answers during the question portion
1. Enforce timing of each segment of the meeting
1. Take good notes on who says what

Second, identify the stakeholders. Sometimes it's domain specific (i.e. frontend/backend)
and sometimes it's role specific (i.e. product managers, engineering managers, etc.)
Ideally the different groupings of stakeholders participate in their own Questionstorm.
There's value in clustering participants by area of expertise because of a phenomenon
that I can only describe as "question inertia." If everyone in a meeting shares
a similar perspective it's easy for initial questions to drive deeper follow up
questions on the same topic. That inertia is harder to feel when questions jump
from topic to topic.

Third, schedule the meeting for one hour and create a meeting doc. Here's a
slightly modified excerpt from a calendar invite for a recent Questionstorm I proctored:

> I'll be proctoring this meeting in a format called a "Questionstorm."
In a Questionstorm participants are given a higher level topic - in this case,
"The product needs to be able to do X" - and participants are only allowed to
ask questions about the topic. The intended outcome is to better understand the
uncertainties of the topic to help dictate future requirements gathering.

Fourth, create the Questionstorm document. Here's a hypothetical example:

> **Disney Questionstorm**
> * Date: 2020-02-03
> * Attendees: Donald Duck, Goofy, Mickey Mouse, Pluto, Dan Na (proctor)
>
> **Topic**: We’d like to create a Disney-focused Javascript library.
>
> **Questions (35m)**
> * [dd] Should we write this in Typescript?
>   * [g] If not, do we need to export type definitions for consuming libraries?
> * [mm] Who is responsible for supporting documentation?
>   * [dd] Can we have generative docs?
> * [g] Will this be an npm package?
> * [dn] Is this likely to be a single repository or a monorepo?
> * [p] Why is Goofy very human despite being a dog but I am not?
> * ...
>
> **Takeaways and Action Items (25m)**
> * [dn] Feels like we need to talk to a product manager for explicit user stories. I'll reach out to Daffy.
> * [mm] There's some prior art by Minnie's team that could inform our roadmap. Will reach out.
> * ...

When the meeting starts, go over the ground rules: for the first 35 minutes
participants are only allowed to ask questions. Record each question as it's
asked with a note of who asks which question (I designate this via initials).
Literally cut off those who try to provide answers with a gentle reminder of the
ground rules.

Once the question portion is over you should leave some time to discuss insights.
I'm less dogmatic about the structure and format of the last 25 minutes than the
first 35 minutes. At a high level it's about identifying salient takeaways. For
example:

* Did we identify any questions that must have answers that no one in this room
can answer? Who can answer those?
* Are there any questions that we can answer now?
* Can we identify and assign any obvious action items?

It may feel paradoxical that asking questions can help _narrow_ scope but it does.
Surfacing user stories, edge cases and peripheral concerns helps you begin to put
boundaries around the surface area of your proposed work, especially when the system
you are changing is large enough that it's impossible to keep a mental model of
it in your head.

Questionstorming surfaces the disparate concerns and incentives relevant to a
proposed change. Those in turn help direct your requirements gathering and inform
the assumptions you'll have to make when executing your work. It's a valuable tactic
for any engineering leader to have in their toolbox.
