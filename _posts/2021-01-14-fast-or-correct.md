---
layout: post
title: Should you build it fast or build it correctly?
subtitle: Building products versus building platforms.
tags: text
---

A few times last year I found myself in discussions weighing the pros and cons of
building something fast versus building it correctly. By "correctly" I'm referring
to taking the normative engineering approach to a problem, regardless of the
pragmatics of timelines. The longer, proper, often more painful way (due to
resolving long-standing technical debt) versus the faster, potentially hackier
way that results in a faster delivery.

I don't love characterizing the two alternatives as "correct" vs "fast," because
the dichotomy makes it seem like "fast" is interchangeable with "wrong." But it's
not, and the choice is not that simple. Also "correct" doesn't need to mean "slow,"
but it often does.

One of my favorite and most repeated quotes is, "in theory, theory and practice
are the same; in practice, they're different." In theory all of the code software
engineers write is elegant, extensible and architecturally sound, but in practice
there are deadlines, staffing considerations and needs of the business to consider.
The [Pareto Principle (or 80/20 rule)](https://en.m.wikipedia.org/wiki/Pareto_principle)
speaks to the unavoidable tradeoff between perfection and good enough.

I find "correct versus fast" to be a common debate between Product Managers and
Engineers. Product Managers push for _fast_ because they are trying to validate
ideas with users as soon as possible. And for good reason; until you have real
signal from users that a product is useful there's no reason to invest dramatically
in its upfront engineering cost. Engineers push for _correct_ because that's what
we're taught - proper code is idiomatic and elegant, and the value of a system
lies in its resilience. Even knowing the hacky solution exists in production
lingers in our heads like a mental thorn.

The best case is a compromise. Ideally Product Managers understand the present
and future leverage of strong engineering practices and Engineers understand
that a well engineered product with no customers is a dead product.

While it will always be more art than science, here's how I've come to think about it:

* If you're building a _product_, bias towards building it fast.
* If you're building a _platform_, bias towards building it correctly.

## Products versus platforms
By "products" I'm referring to the development of user-facing features. The
value of products is customer happiness/product-market fit, which is incredibly
elusive and makes iteration speed critical. When building products first focus
on discovering value and then invest in making them resilient.

By "platform" I'm referring to the software layers on which products are built.<sup id="footnote-1">[1](#platforms)</sup>
The value of a platform is organizational leverage - how does it empower current
and future product development? How easy is it for new engineers to grok the
mental model of how it works? Are the primitives simple and extensible? Invest
in building strong foundations for platforms. A hacky platform quickly becomes
an onboarding, upgrading, and maintenance nightmare.

Which invites the next question: when can you tell when you're building a
product or a platform? The distinction is not always obvious, but here's one
heuristic I find useful:

> TEST: If the thing you're launching performs poorly, will it get killed or
will it live on? In other words, do you need to build this thing for future
reasons regardless of the immediate performance of this version?

If it can get killed, it's a product.

If it will live on, it's a platform.

For example, my team at work is the engineering owner of internationalization.
Many of our projects require both shipping a feature to new users while evolving
the underlying architecture of an existing, long-in-production codebase in order
to do so.

Let's see how this heuristic applies _in theory_: We want to release an
existing feature to _n_ new markets, and we need to add additional language
support across all products in order to do so.

> TEST: If the feature release to the new markets fails, will the release get killed?

Yes. If the feature performs poorly in these new markets, maybe it's inappropriate
for the customers in those markets. If metrics indicate poor customer behavior,
the launch will be killed.

The feature is a product.

> TEST: If the feature fails, will the work to add additional language support
get rolled back?

No. We need additional language support moving forward anyway, and regardless
of the performance of this release we will build and experiment with other
market-specific features in these new languages.

The additional language support is a platform.

There is a tension here. The product component needs to be done quickly and the
platform component needs to be done correctly. How you proceed really depends on
the urgency of the business context, but in general if you know where the platform
is going, you can use [good tech debt](https://engineering.squarespace.com/blog/2019/three-kinds-of-good-tech-debt)
to ensure that the feature is launched fast without sacrificing its long term
ability to be integrated into the platform.

Of course, _in practice_, the lines between product and platform are often blurry -
many projects are both product and platform, or start as one and end as the other.

I remember using Facebook before the launch of News Feed, when searching and
reading individual profiles was the primary method of engagement. And then
[News Feed launched in 2006](https://www.weforum.org/agenda/2016/09/facebooks-news-feed-is-10-years-old-this-is-how-the-site-has-changed)
and evolved into the backbone of the Facebook product experience. I can only
imagine that News Feed started as a product experiment and, after an explosion
in user engagement, quickly grew into a platform upon which many other products
were built for years afterwards.

This commonly unexpected transition makes the tension between product speed and
platform diligence important to continually revisit. In a long-enough time horizon,
your most successful products often become platforms, which forces you to
periodically reconsider their architectural foundations and iterative pace.

---

<a name="platforms">[1]</a>: "Platform" is a loaded term in tech. I'm using
"platform" within this post to refer to the shared services/abstractions/codebases that
support applications at a company. There's an entirely different conversation
around platforms in reference to corporate positioning - [Shopify and the Power of Platforms](https://stratechery.com/2019/shopify-and-the-power-of-platforms/)
being a worthwhile example to read - which is similar in spirit but an entirely
different topic. [↩](#footnote-1)
