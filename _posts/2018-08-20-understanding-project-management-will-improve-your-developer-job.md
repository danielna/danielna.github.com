---
layout: post
title: Understanding Project Management Will Improve Your Developer Job
subtitle: Shipping is about intention, not luck.
tags: text
---

Last year when I was between jobs I asked a friend of mine how he liked his new gig:

> Him: "It's great!," he said. "We basically have no managers and don't have to deal with stuff like Jira."
>
> Me: So how do you know what to work on? Who tracks the company priorities?
>
> Him: "Hmm, I'm not sure. Engineers basically decide what to work on themselves."

His company is small enough that this might work, and several years ago this would've sounded like a utopian ideal. Early in my career I developed an "I hate meetings", "Scrum is a waste of time", bureaucracy-allergic coding agenda. [[0]](#footnotes-0) Any interruption to my day was an interruption in Getting Things Done! I went so far as to write it on my LinkedIn profile.

But experience has shown me that in companies of a sufficient size this is a naive approach to work. At a startup you may wear multiple hats -- product manager/engineer/CTO -- but at a company large enough for disparate, focused teams a lack of management direction becomes a major blocker. Your team's work is useful or useless in the context of other teams' work. All of that "bureaucracy" -- meetings, scrum, Jira, etc. -- is a means of sharing and understanding that context.

Here's a statement I believe to be true: developers are happier when they are busy. It's 100% consistent with my own experience; the days in which I can become entrenched in solving a problem are by far my best and fastest days in the office. Various engineering thought leaders have written about the merits about giving time to developers to be "locked in" and the risks of meetings disrupting that time. I totally agree that uninterrupted work time is important.

But rallying completely against the safeguards that make your busyness meaningful -- useful meetings, Jira, project management practice -- is missing the forest for the trees. Because here's a statement I believe in even more than the first statement: working really hard on meaningless tasks/projects will make you hate your job.

Time and again I've witnessed engineers work really hard on projects that either should have never been started in the first place or ballooned in scope to unattainable levels. They execute great engineering work for projects that are cancelled or thrown away. And the results are always the same: it is 100% effective in burning them out and serving as the first step out of the company. To make matters worse it's the ones who invested themselves most -- often the best engineers -- who leave first.

These observations were more of a quiet, passive discontent in the back of my mind until I became an engineering manager. Until then I thought project outcomes were partially a result of the "luck" of how projects went: some good, some bad. As engineers we were simply subject to the inevitable ebb and flow of project success.  But as I began to read management books -- particularly [High Output Management by Andrew Grove](https://amzn.to/2M6r957), which I still regularly re-read -- I began to craft a frame of reference around what I was feeling. And I realized luck has nothing to do with it.

Project outcomes are a function of intention. Asking and answering the right questions can drive a team towards clarity around the goals and importance of their work. And as someone who wants to be accountable to my own fulfillment at work, [developing smells](http://blog.danielna.com/2015/02/07/developing-my-sense-of-code-smell.html) around projects that are heading in the right or wrong direction is an investment in my own success and happiness.

I've distilled my times of greatest happiness at work to a few key characteristics: 

1. I am busy.
2. I don't work on an island.
3. My work is important to the business.
4. I ship.

The fourth point is the most important. None of the other three matter unless you ship.

As a manager I did my best to ensure that our scrum/Jira practice optimized for these characteristics and I think it was successful, as our team had an [outsized effect on the organization despite our small size](http://blog.danielna.com/2017/09/14/creating-an-accessibility-engineering-practice.html).

I've moved back to an individual contributor (IC) role at my current job but my time as a manager has changed how I approach planning and executing work on teams. I'm not very dogmatic about specific procedural details (i.e. "we must use fibonacci flash cards for ticket estimation!") but I do think there are driving questions that any manager/IC/team can ask themselves to ensure their team's success and happiness.

## Driving questions towards project management clarity

### What did we just finish, what are we working on now, and what are we working on in two weeks?

I was in a meeting of managers once and one of my peers mentioned that they could see the value of Jira but didn't think they could convince their team to use it. "They hate dealing with tickets and the Jira UI is so complicated [[1]](#footnotes-1); it'll be a tough sell."

Here's the thing: Jira isn't the sell. Jira is a means to an end. [[2]](#footnotes-2) Forcing an unwilling team to use Jira without convincing them why it's important is like trying to force people to run on a treadmill before convincing them about the merits of maintaining their cardiovascular health.

Tracked, meaningful work is the sell. Instead of being prescriptive about project management implementation details (e.g. "we must see a decreasing burn down chart every month!" [[3]](#footnotes-3)), I recommend being prescriptive about outcomes. If you're in charge of a team or set of teams, create a straightforward ask: every month I want a granular list of the work you've completed, the work you're doing now, and the work you'll do next.

For the previous/current work question, it is nearly impossible to regularly provide an answer without a ticketing system. Common alternatives to a ticketing system create an unsustainably annoying amount of manual overhead, including a constantly outdated spreadsheet or some mix of "hey Dan, what stuff did you ship this month?" I guarantee engineers will _really_ hate filling out a status report on a monthly basis and will often misremember their own work. 

Suddenly managing a suite of tickets becomes a much easier sell: keep your tickets up to date and we can automatically generate reports from those tickets. [[4]](#footnotes-4) And as a significant side benefit to the individual engineer, a record of closing meaningful, granular tickets is a good way to build a case for promotion. All the more reason to track your work.

Needing to plan future work is a good forcing function for asking hard questions about your current work. Are we tracking the goals of shipping the things we originally set out to ship? If not, are we spread too thin? Do we need more resources (rare) or focus (common)? 

A sprint planning meeting is a good venue to ask these questions. The inability to granularly plan work for the next two weeks is a smell that your work isn't cohesive or building towards something.

### Is anyone on an island? Do we have any single points of failure?

When people think of Single Points of Failure (SPOF) they often think of a single person in charge of an entire system or product. The downsides of working this way are well known: it's a risk to the organization ([if that person leaves everyone is screwed](https://en.wikipedia.org/wiki/Bus_factor)) and it promotes burnout. Some people prefer working on an island but most people don't.

Fortunately, system-wide SPOFs are generally (hopefully!) rare. Team-based SPOFs are much more common and likely to affect the output of your team on a weekly basis. Say you break up a large project into granular tickets, some of which have a dependency on others. Person A is working on a subsystem that's a prerequisite to Person B's work. Then Person A is sick or goes on vacation for two weeks. Meanwhile Person B is blocked on their work and has no idea what Person A has done.

This happens ALL THE TIME. It's super frustrating for everyone except Person A who's spending two weeks sitting on a beach sipping a drink with a tiny umbrella.

The fix for SPOFs is adopting practices that promote context-sharing.

On a daily basis I suggest adopting a practice of commenting extensively -- and I mean _extensively_ -- on any in-progress tickets. The ticket should accurately reflect the context you've gained over that task at any given time. Did you try a different approach in code that failed? Explain the approach and leave a gist as a comment. Did you have a slack conversation with a person on another team that clarified an implementation detail? Copy/paste that conversation into a comment. Was an email exchanged? Copy/paste that email.

Extensive commenting helps move away from the island problem by making tickets truly interchangeable among teammates. It also promotes collaboration/shared context around different streams of work within a team. From reading Person A's comments I can understand how they approached their problem and found their solution without ever working on it myself. It's a great way to learn from each other.

Another SPOF-mitigating practice is a weekly meeting to estimate tickets. Superficially the goal of ticket estimation is assigning a complexity number to tickets to track team velocity. That's not actually the main goal. The main goal of a ticket estimation meeting is shared context. Explaining the details of a ticket enough for everyone to come to an agreement about its complexity requires everyone to ask questions about the work involved. It forces teammates with more context to provide clarifying details to teammates with less context in order to reach quorum on a prevailing complexity value.

Shared context eliminates islands.

### Is our work important to the business?

The degree to which projects align with business objectives sets their priority. This determination can be particularly difficult based on the type of team you're on. While the business impact of a payments team or product team may be more obvious than an SRE or infrastructure team, it doesn't make understanding business alignment for these teams less important; if anything, it makes it _more_ important.

For the last ~6 years or so I've worked in the engineering niche of [frontend infrastructure](https://www.smashingmagazine.com/2013/06/front-end-ops/), which focuses on the systems that manage building modern frontends. My world is concerned with the tools/workflows that my coworkers use to build customer-facing user interfaces and the delivery and performance of those interfaces.

The landscape of frontend tooling and frameworks changes constantly. The JavaScript zeitgeist of today is tomorrow's laughably-bad-decision-in-retrospect. In a domain where twitter feeds and blog posts are a continuously updating stream of best practices and technologies, it often feels like your build and workflows are constantly outdated. Assuming your resources and time are finite, how do you decide which of these best practices and new technologies are worth implementing and which aren't?

The answer is business/product priority. If best practice/technology X doesn't somehow align with a business/product goal then it's not worth pursuing until it is. 

I'll be the first to admit that the mappings of infrastructure work to product goals can be hard to see. You'll often have to work (or communicate) to discover what they are.

For example, say your company is expanding to international markets. There are some obvious infrastructure implications, like [building a reliable delivery system for translations](https://engineering.squarespace.com/blog/2018/building-a-system-for-front-end-translations) or ensuring fast content delivery to users in distant locations. But there are also less obvious implications that may require domain knowledge to identify. For example, many developing markets are heavy users of the mobile web. How will the size of our mobile web production assets affect performance on those devices?

It's extremely important for infrastructure teams to work with product managers or product owners to identify these opportunities. Many product managers aren't thinking about mobile web asset sizes but are looking at real-world usage data. Providing opportunities to explore the intersection of business goals with infrastructure domain expertise can identify non-obvious but important work streams.

> Okay, Dan. But what about plain old tooling upgrades? We might not be able to map upgrading a framework to a conversion metric but that doesn't mean providing regular upgrades isn't valuable.

You're right. In circumstances like these I like to borrow a concept from Andrew Grove: organizational leverage.

A high leverage activity is one which has a disproportionately large, positive impact on the output of an organization. Leverage is another useful lens of evaluation. Does this project have a significant, positive impact on the speed of product development or platform stability?

From the frontend infrastructure perspective: say we're considering prospective projects to upgrade our build pipeline, support Typescript, or support a popular new testing library.

If we have a long and slow build time, upgrading the speed of the build pipeline would be a high leverage activity because it'd increase the speed at which product engineers can ship code to production. Has a team used Typescript on a project and proved that it significantly reduced bugs and improved refactoring times? Maybe it's worth applying those lessons across more projects. Does the hot new testing library provide a few functional enhancements but not much of a practical difference over the existing library? Maybe it's not worth an upgrade right now. Making these decisions is more art than science, but the act of grappling with these decisisons is valuable.

Base your priorities on company priorities and be relentless about revisiting them. A clear understanding of priority will help clarify which projects to start, stop, abandon or finish. And it'll help avoid the worst scenario where your team does great work on an ultimately meaningless task.

### Do we ship?
"Do we ship?" is the most important question. All the other questions build to this one. You need to ship.

This might sound like a stupid statement, but it is so much easier not to ship than to ship. The [80/20 rule](https://en.wikipedia.org/wiki/Pareto_principle) is real; the last 20% of a project is 80% of the work. The last few weeks of a project launch can feel like an endless and insurmountable list of clean up tasks. There's likely a marketing/education effort. There are questions about monitoring and rollback strategies. The difference in work to get a project production-ready vs indefinite-prototype-ready is huge. But it's a hurdle worth overcoming because it matures your team and its processes. And there is no better feeling in software engineering than ship days.

Project management is not about bureacracy or meaningless overhead, it's about getting to ship day. Getting to ship day means ensuring that there's a defined end goal, useful tickets are created and completed, progress is meaningfully tracked, scope is held in check and no detail is left unturned.

Shipping is also generally good signal for overall team health. It's rare that a team with a toxic culture and arbitrarily shifting priorities ships regularly. You also can't ship regularly by being spread too thin or working on the wrong things.

Effective teams ship and ineffective teams don't. It's hard to have job satisfaction or career advancement on an ineffective team.

## Be accountable to your own happiness
Effective project management is a self-reinforcing pyramid of accountability. [[5]](#footnotes-5) At the bottom level, engineers are accountable to the tasks they're assigned, with the trust that those tasks build meaningfully towards shipping a useful project. At the middle level, managers are accountable to the projects their team(s) work on, trusting that those projects build meaningfully towards a successful business strategy. And at the top level, organizational leaders are accountable to defining and articulating that business strategy. 

The resulting overhead of project management -- meetings, tickets, etc. -- are safeguards against the ultimate worst outcome: building wrong or useless things. There's no more demotivating sentiment than feeling like your work is a waste of time. And besides, the opportunity cost of building useless projects will ultimately kill your company. [[6]](#footnotes-6)

Whether you're a manager or IC, I encourage understanding and evangelizing the merits of strong project management practice as an investment in your own job satisfaction. You can spend your career hopping from company to company on the hopes of landing on a team that shares the characteristics of a job you enjoy or own implementing those characteristics wherever you go. 

Remember: meaningful work is not about luck, it's about intention. Be intentional.

## Footnotes

<a name="footnotes-0">[0]</a> I started my career in government contracting. I'd say the bulk of my 9-5 was spent attending meetings, the majority of which I wasn't expected to say anything in.

<a name="footnotes-1">[1]</a> For the record, the goal of this post isn't to poo-poo on Jira. I actually really like Jira. People have justifiable problems with it because it's infinitely configurable and not necessarily beginner friendly but I personally love the feeling of setting up a new clean Jira board. It feels like a fresh start to do good work.

<a name="footnotes-2">[2]</a> I don't have strong opinions on project management tools in terms of Jira vs. Pivotal Tracker vs. Trello or whatever. I mention Jira over and over again because it's what I'm used to. The choice of tool doesn't really matter. The important thing is that you have a means of creating and updating a history of work. 

<a name="footnotes-3">[3]</a> I've never seen a useful burn down chart. It's possible with a super tight, end-to-end project management workflow where all the tickets are broken down and estimated perfectly every sprint, but that's a unicorn I haven't seen IRL yet. 

<a name="footnotes-4">[4]</a> In Jira you do this by creating a Release at the end of the Sprint.

<a name="footnotes-5">[5]</a> It's a pyramid because higher levels of the pyramid depend on lower levels. It frankly doesn't matter what your business strategy is if your teams can't ship projects. But an ill-defined business strategy means your effective teams work on useless things (and you'll probably have a retention problem).

<a name="footnotes-6">[6]</a> This is also demotivating.
