---
layout: post
title: Choosing the Management Track
subtitle: How the IC and EM tracks are different, and why I switched back.
tags: text
---

Several months ago a friend of mine reached out to me because he was considering
changing from an individual contributor (IC) role to an engineering management (EM)
role at work. Given the fact that I've bounced back and forth a couple times, he
wanted to pick my brain as to what I thought the tradeoffs were and why I
ultimately went back into management.

He's not the only person to reach out to me about this topic (in fact, a different
friend reached out a week later) so I figured it'd be useful to write a blog post
consolidating my thoughts. I'll separate this post into two sections: some
significant and perhaps unintuitive changes that are relevant to someone
considering moving from IC to EM, and my personal motives.

## The differences

### 1: You won't code anymore.

I once heard some tongue-in-cheek advice about moving to management: "If the
thought of never coding anymore turns your life to ash, don't move to management."
Turns out it's true.

The "should managers still code?" question is probably the most hotly debated
question about the role change, and I'm taking a side: no. Maybe not immediately
after the switch, because your team may be small enough that it needs your
technical contribution or you may still be the subject matter expert, but as
you climb the management ladder you will move further away from doing any
implementation work. In fact, I'll argue that managers who cling to coding work
hold back the output of their team.

A popular assumption is this is an outflow of your technical skills becoming
stale. It's not. I'm not saying it's impossible, especially on a very extended
timetable that involves core structural shifts in industry practice, but I think
those shifts (and your inability to ramp up on them assuming a strong technical
base - see "[The Engineer/Manager Pendulum by Charity Majors](https://charity.wtf/2017/05/11/the-engineer-manager-pendulum/)")
are rare. The principles of sound software engineering practice are timeless.
But either track requires focus. It's not that you can't code, it's more that
you shouldn't - your schedule simply won't allow it.

As a manager, your schedule will become so unavoidably non-deterministic that
you cannot be relied upon by the rest of your team to ship code changes on an
expected cadence. You won't be able to respond to questions or pull requests
involving the code you previously wrote. You won't have the bandwidth to ship
updates to that code when requirements change. And in the big picture this is a
problem, because teams distributing and shipping work in concert is the backbone
of successful software development.

The reason for this non-deterministic schedule is rooted in my second difference:

### 2: Management forces you to care more about everything.

Generally speaking, as an IC the measure of your impact is your individual technical
contribution: work scoped, code successfully deployed to production, RFCs proposed
and reviewed, etc. While this often involves working with others, at the end of
the day you are largely in control of the factors that determine your output. You
can sit at your desk and work more hours. You can write more / better code. You
can add more tests. The success or failure of your technical efforts have more
to do with your effort than anyone else's.

One of my beliefs about management is borrowed directly from [High Output Management by Andy Grove](https://amzn.to/30XV84J):
the measure of a manager is the output of the organization underneath them. Unfortunately
the factors that sum to a team's output are far fuzzier than the factors that sum
to an IC's output. And it's not as simple as adding up all of the discrete technical
outputs of your ICs because team output is measured via the delivery of coordinated,
high-quality projects over time.

Here are some not uncommon situations:

* A team of talented ICs ships high quality work. But they feel no buy-in or
camaraderie within the team or greater organization, and the entire team turns
over within a year. The constant hiring and onboarding makes it difficult to rely
on this team for time-sensitive tasks or reliable ownership over part of a codebase.
* A set of teams spends an extended time working on a project that gets killed
before launch. Turns out it wasn't the right thing to build. The ICs on that team
turned out high quality work but to a useless outcome.
* A team of talented ICs ships high quality work, but they have one or two very
senior brilliant jerks. Other teams do not like engaging with these brilliant
jerks so they avoid interacting with the team. Consequently the high quality work
of this team does not have organizational impact.

A common thread between each of these scenarios is that ICs are delivering high
quality work. Another thread is that the high quality work ultimately doesn't
benefit the organization. Retention problems, working on the wrong things, toxic
cultures - these are all examples of management failure.

There's no checklist for building non-toxic cultures or a team that ICs want to
stay on. Engineering teams are fortunate if they're told exactly what to build
every quarter to meet the growing technical and business needs of the company
but I've never found that to be true. The poor definition of these ideas makes
management hard. And it puts the burden on the manager to maintain their own
level of vigilance that all of these things - personalities, priorities, culture,
etc. - stay on track.

As a small but illustrative example of something that's different as an IC than
a manager: morning standup. When I was an engineer, there were more than a few
times during morning standups when I didn't pay attention unless I was giving
my own update. And frankly it didn't seem to matter much, especially if the other
updates were concerning different workstreams than the one I was currently focused
on.

As a manager, I can't afford not to pay attention to every update during standup
because I am ultimately accountable for the delivery of _every workstream_. Not
only am I trying to identify and surface team-wide blockers, but I need to know
when a junior teammate sounds like they're spinning their tires or when a senior
teammate sounds burnt out. I'm mentally noting points I need to follow up on
during my weekly 1:1s, what projects feel like they're falling off original
timetables or communication problems my teammates are encountering across the
organization. Is a teammate overwhelmed? Is a teammate dragging their heels?
What if I'm hearing reports that a teammate has been toxic in meetings? These are
all concerns running constantly in the back of my mind.

This is the root of the non-deterministic schedule from the first point. Say I
smell one of these things - a teammate is very disengaged and unhappy? A project
is going off the rails? A teammate suddenly gives their two week notice? These
are my fires now.

Gone are the weeks of deterministic bandwidth calculated via possible work hours
divided by ticket estimations. And that unpredictability means my outdated pull
request that unblocks another teammate goes days or weeks without being merged.

Is there room every once in a while for an EM to work on a non-blocking PR just
to scratch their coding itch? Probably. Is the work time you spent working on that
nice-to-have PR better spent on a management responsibility? Probably.

My advice: find time to scratch the coding itch outside of work.

A side effect of caring more about everything means management costs you more
emotionally. When hardship or tragedy strikes the life of a teammate and it affects
their ability to work, I'm often the first to know. Depending on the sensitivity
of the issue sometimes I'm the only one to know. Not only am I responsible for the
practical fallout of their absence, but I wouldn't be successful in my job if I
didn't genuinely care about the wellbeing of my teammates. And in my experience
it's not free to know people you care about are suffering.

### 3: Management creates an unavoidable power hierarchy.

As a manager you have direct power to decide your reports' continued employment
and compensation in a manner in which they cannot do for you, which means you
have more power over them at work than they do over you. This isn't a statement
of right or wrong, this is a statement of fact.

I think there are a few non-obvious practical implications of this power hierarchy:

**You will feel more compelled to toe the company line.**

You represent the company now within your sphere of influence. While I don't
think moving into management means you lose your capacity for independent thought,
the health of an organization often depends on its leaders' ability to disagree
and commit.

This particularly comes to a head during times of crises, as those on your team
will look to you as a steadying force and source of information. By virtue of your
title you may know not-yet-public information and be expected to keep that information
private until the appropriate plans are in place, all for the good of the company.
Sometimes that news will be devastating and you'll take heat for keeping it quiet
from people who trusted you. That's part of the job.

**It can be hard to manage friends.**

The foundations of friendship are things like equality, honesty, and transparency,
principles which don't always jive with a management relationship. Management is a
power hierarchy (`!equality`), and sometimes you'll have to disagree and commit or
toe the party line (`!honesty` / `!transparency`).

The alternative is special treatment for your friends, which is a management failure
because nepotism undermines your credibility as a leader. And in the worst case,
you are in the unenviable position of having to terminate a friend's employment.
That too is part of the job.

**You can't joke around the same way.**

Here's a a bad joke you can make as an IC that doesn't land as well as a manager:
"Welp, you broke production. Pack your things, you're fired."

The power dynamics of management are serious and livelihoods are at stake. Don't
trivialize them with jokes.

### 4: You need to be technical enough to intervene.

[Management is a technical job.](https://twitter.com/kellan/status/1302004327188398080)

The measure of a manager is the output of the organization underneath them. And
while there are a lot of responsibilities and tasks that sum to "output," one of
the major ones for engineering managers is accountability. You need to be technical
enough to keep your team accountable to a strong engineering outcome.

As a general life principle, I don't think you can hold people accountable to
something you can't demonstrate yourself. At an IC level, it's hard to mentor and
grow someone in an individual technology if I am not much more experienced than
they are in that technology. At a management level it's hard to ensure a team is
executing if I have never demonstrated and cannot explain the principles of team
execution.

I'm not saying you are expected to be a technical subject matter expert as a manager.
In fact, at most large tech companies the parallel IC track to the EM track makes
that suboptimal. But you must have real smells and opinions on how technical projects
are delivered, agnostic of their implementation details. And you must be technical
enough to know when a project feels like it won't deliver and intervene appropriately
to force it back on track.

How you intervene is strategic thinking rooted in technical experience. Can you
cut scope without sacrificing critical functionality? Can you choose a less user
friendly solution but fortify it with significantly more documentation? Will adding
more engineering resources help? As you explore alternatives, what are the downstream
effects on other engineering or business teams?

Another phrase from Grove's book that I think about often is "delegation is not abdication."
As the manager you are responsible for the technical delivery of your teams projects
even though you're not performing any implementation. Delegating work as a means
of absolving responsibility from outcomes is a management failure mode.

## My motives for the management track

After a list like that, you may ask why anyone would want to pursue the management
track at all. In fact, more than one person who has contacted me decided to stay
on the IC track after I shared points similar to those above.

To answer that question for myself:

### 1: The tasks of management align well with some of my intrinsic skills.

Two tasks that come easily to me are writing and public speaking. I'll offer the
caveat that this isn't a _motive_ for pursuing management, but rather a very
convenient alignment of intrinsic skill and day-to-day management responsibility.
It makes the job of management easier.

Regarding writing: I don't really know how to put this in other terms, but I
simply don't struggle putting my thoughts to paper. In practice this means I can
produce high-quality written artifacts quickly. And because written artifacts are
a common output of many management tasks, this helps me considerably with time
management. Assuming I've collected the relevant information beforehand, I find
that I don't have to dedicate long time blocks to writing things like roadmaps or
reviews, and any stints with writers block are relatively short lived.

Regarding public speaking: this is less an "intrinsic" skill than one I've developed
through a lot of practice, but at this point in my career I'm a very comfortable
public speaker. I've spoken at a [number of conferences](https://talks.danielna.com).
I've delivered countless internal presentations at jobs, both company-wide and for
smaller groups. I'm comfortable enough with public speaking that the opportunity
to address a large group of people genuinely fills me with more excitement than
fear (which is the complete opposite of early in my career).

This is relevant because I think public speaking is an unavoidable responsibility
of leaders, especially as you climb the corporate ladder. You will inevitably run
large meetings or present to executives. And one key responsibility of leaders is
to motivate and inspire, so it's critical that you excel when given opportunities
to communicate widely across your organization.

### 2: I want to continue to validate my opinions on the execution of engineering work and culture because I'd like to run an engineering organization one day.

One of my long-term career goals is to run an engineering organization. Running
an engineering organization is a job that I imagine pulls you in 100 different
directions: recruiting, leveling, architecture, shipping, retention, compensation, etc.
And as the head, the organization thrives or is capped by your leadership.

When that day comes I think it's critical that I'm one of the strongest managers
at that company. I don't think there's a convenient book or silver bullet for
developing that skill. The only way to get better at managing is to actively manage -
to grow and run teams, ship to production, and build and maintain a culture consistent
with a [management philosophy](http://management.danielna.com) that I continue
to hone over time.

### 3: I don't want to bemoan a lack of ethnically diverse representation at engineering leadership levels without doing something about it myself.

I'm an East Asian male. I'll be the first to admit that claiming that East Asians
are underrepresented in technology roles is ludicrous. In fact, there have been
significant numbers of East Asian engineers at every job I've ever had.

However, I've never worked at a company that's had East Asian representation at
engineering leadership levels anywhere near commensurate to the numbers at lower
engineering levels. Nor do I see much East Asian representation among featured
speakers at management conferences.

[Stereotypes](https://www.tolerance.org/magazine/what-is-the-model-minority-myth)
[exist](https://www.imdb.com/title/tt0366551/characters/nm0158626) that harm the
perception of those of East Asian descent as leaders. I've lived these stereotypes
in various forms, both throughout my lifetime and via personally witnessing the
egregious under-compensation of a talented but non-confrontational and non-American-born
coworker at a previous job.

One reason I pursue management is I believe ethnic diversity in engineering leadership
is important and creates better outcomes. And the best way I can think to make
that change is to get there myself by demonstrating continued excellence in management
roles over time and advocating for my own visibility.

### 4: My favorite thing at work is to see people and teams self actualize.

Have you ever been an IC on a team that was a total joy to work on? Where you
actively looked forward to coming to work, confronted hard technical problems
with people you loved working with, and regularly shipped meaningful, business-impacting
projects that embodied engineering excellence? I have.

Have you ever worked with a manager whom you really respected? Who respected your
skills and interests, treated you fairly in the midst of your mistakes, celebrated
your wins, gave you a safe amount of autonomy for your level, sponsored you internally
and externally and insured visibility and recognition at comp/promotion time? I have.

And as I look back on it, these were the same teams. The best teams I've been on
had the best managers, and those were the times I grew most as an IC.

Landing on a well run team with a great and capable manager can feel like dumb
luck but it's not. It's intention. It's establishing and enforcing norms of behavior,
expectations, psychological safety and output. It's providing the procedural bounds
that allow engineers to perform their best work and recognizing them for it.

Management is a privileged position to provide that environment for others. And when
it's working - the team is healthy and collaborative, ICs are growing via stretch
projects, and you play a role in the development of autonomy/mastery/purpose of
a teammate - there is no better feeling in the world.

### 5: Companies ultimately succeed or fail by their coordinated execution, culture and leadership.

[As a staff engineer](https://staffeng.com/stories/dan-na) I became comfortable with
scoping and executing wide-reaching technical problems. I still love participating in
those sessions. But there's a level of abstraction upstream of that scoping meeting
that I think is more critical for oganizations to get correct: "given the current
context of our business / staffing / priorities, should we even build this thing?
And if the answer is no and it still needs to be built eventually, how do we get there?"
I'm now more interested in that discussion than the scoping discussion.

I think the upstream discussions are the ones that make or break companies. I'm
not discounting the technical leadership of senior ICs - it is critical - but I
more often find alignment, priority and direction to be more of a blocker to a
company's success than sheer technical ability.
