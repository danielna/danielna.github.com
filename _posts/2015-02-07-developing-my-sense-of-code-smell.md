---
layout: post
title: Developing My Sense of (Code) Smell
subtitle: And thoughts on taste by Ira Glass
tags: text
redirect_from: "/2015/02/07/developing-my-sense-of-code-smell.html"
---

> Nobody tells this to people who are beginners, I wish someone told me. All of us who do creative work, we get into it because we have good taste. But there is this gap.
>
> For the first couple years you make stuff, it's just not that good. It's trying to be good, it has potential, but it's not. But your taste, the thing that got you into the game, is still killer. And your taste is why your work disappoints you.
>
> A lot of people never get past this phase, they quit. Most people I know who do interesting, creative work went through years of this. We know our work doesn't have this special thing that we want it to have. We all go through this.
>
> And if you are just starting out or you are still in this phase, you gotta know its normal and the most important thing you can do is do a lot of work. Put yourself on a deadline so that every week you will finish one story. It is only by going through a volume of work that you will close that gap, and your work will be as good as your ambitions.
>
> And I took longer to figure out how to do this than anyone I've ever met. It's gonna take awhile. It's normal to take awhile. You've just gotta fight your way through.
>
> <footer><cite><a href="https://www.youtube.com/watch?v=BI23U7U2aUY" target="_blank">Ira Glass, Host of This American Life</a></cite></footer>

I've been thinking a lot more about the idea of
<a href="http://martinfowler.com/bliki/CodeSmell.html" target="_blank">code smells</a>,
which is really more of a generic idea than its name implies.  Basically, a "smell"
occurs when something "smells" wrong; something at the surface appears to imply a fault at deeper levels.

When your date is nice to you but mean to the waiter?  That's a date smell.

I realized recently that my sense of code smell is a lot different than it was a year ago.
And its more multi-dimensional to things other than just code structure.

There are some obvious smells when it comes to actually writing code: DRYness,
testability, modularity, readability, etc.  I find myself thinking about these
things a lot more now than I did before, largely due to working with skilled programmers.
But the most interesting code smells I've experienced at work, particularly working
on an infrastructure team, are smells around when our work is actually finished.
If we <a href="https://codeascraft.com/2015/02/02/transitioning-to-scss-at-scale/" target="_blank">build and release a successful product internally</a>,
at what point is that tool considered done?  When we look at how engineers use our tools
and see their gains/pain points months after our release, when is it time to revisit
the original constraints and assumptions we made when creating the tool in the first place?

Infrastructure work is unique in that our product roadmaps aren't very deterministic.
We can make the assumptions that we'll get to A, B, and C in the next X months,
but supporting active engineers implies an indefinite feedback cycle that lives
for as long as our tool lives.  Of course we respond to fires, but what about the
smell of smoke?  What if something doesn't "feel" right, even though it works?

There's a balance between wanting to do things fast and do things right. It's
always more fun to start the next greenfield development project than clean up
the loose ends of the project we finished months ago.  But that doesn't make it
less important.

Experience, intuition, taste.  It's all working on something until it no longer smells.
