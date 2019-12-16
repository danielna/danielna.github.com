---
layout: post
title: Creating an Accessibility Engineering Practice
subtitle: Accessibility is not a feature, it's a requirement.
tags: text
---

I was a founding engineer and then the engineering manager of Etsy's first accessibility team for about a year, from mid-June 2016 to mid-June 2017. We were a small team of three, but [Cameron Cundiff](https://twitter.com/ckundo)'s deep subject matter expertise/strategic vision and [Kristyn Reith](https://twitter.com/krreith)'s work ethic and quick study of a completely new technical domain resulted in an organizational impact that far exceeded our team size. I will be forever proud of how much we accomplished.

I very intimately understand how making your product accessible can seem like an intractable problem, especially at large companies with large codebase(s) and lots of teams. I still remember the meeting in 2015 that kicked it all off. Our manager at the time asked, "what should we work on this year?" Someone asked, "what's the deal with accessibility?" We all looked at each other and shrugged. Beyond best practices like associating form labels with inputs and being moderately confident that alt attributes on images were important for some reason none of us had a real understanding of how accessibility worked.

One of our overarching goals as a team was to teach. We knew that any inaccessible interfaces built at the company weren't a function of apathy or malice but ignorance. Once engineers/designers knew how their design/UI decisions negatively impacted real users, could they ever again willingly create an inaccessible design? We weren't looking just to impact the products they built at Etsy but also the products they built for the rest of their careers.

While the lessons are still fresh I want to write the blog post that I wish I had read when I was first starting down this path, in the hopes that it gives you insight into possible steps and the belief that crafting culture around accessibility is possible. Teaching coworkers at your company about accessibility will only raise the engineering standards across our industry moving forward.

Accessibility is not a feature, it's a requirement.

## Disclaimers

1. I no longer work at Etsy and the contents of this post is not speaking on behalf of the company. This post is 100% a reflection of personal experience and opinion.
2. Our focus was web accessibility. Mobile accessibility is very important, but I don't have as much experience with it.

## Table of contents

{:.toc}
* [Quick note: what is a11y? What are assistive technologies?](#quick-note-what-is-a11y-what-are-assistive-technologies)
* [Paradigm shifts](#paradigm-shifts)
  * [The accessibility tree](#the-accessibility-tree)
  * [Keyboard accessibility](#keyboard-accessibility)
  * [How do AT users interact with websites?](#how-do-at-users-interact-with-websites)
* [Changing culture](#changing-culture)
  * [The business case](#the-business-case)
    * [Legal](#legal)
    * [SEO](#seo)
    * ["How many people with disabilities use our site anyway?"](#how-many-people-with-disabilities-use-our-site-anyway)
  * [Can you hear from real users? (User research is amazing)](#can-you-hear-from-real-users-user-research-is-amazing)
* [Remediation strategies](#remediation-strategies)
  * [Automation](#automation)
  * [Manual accessibility review](#manual-accessibility-review)
  * [Bake accessibility into your UI/component library/styleguide](#bake-accessibility-into-your-uicomponent-librarystyleguide)
  * ["Accessibility is solved at the design stage"](#accessibility-is-solved-at-the-design-stage)
* [Quick wins / where to start](#quick-wins--where-to-start)
    * [Familiarize yourself with WCAG 2.0](#familiarize-yourself-with-wcag-20)
    * [Get plugged into the #a11y community](#get-plugged-into-the-a11y-community)
    * [Add a "Skip to Content" link](#add-a-skip-to-content-link)
    * [Fix your heading outlines](#fix-your-heading-outlines)
    * [Fix your forms](#fix-your-forms)
* [Everything else](#everything-else)
  * [What's the deal with ARIA?](#whats-the-deal-with-aria)
  * [What's the deal with screen readers?](#whats-the-deal-with-screen-readers)
  * [What are other organizational accessibility wins to consider?](#what-are-other-organizational-accessibility-wins-to-consider)
    * [Real-time captioning](#real-time-captioning)
    * [Video captions](#video-captions)
    * [Invite guest speakers](#invite-guest-speakers)
  * [Tools and resources that we actually used](#tools-and-resources-we-actually-used)

## Quick note: what is a11y? What are assistive technologies?

"a11y" is a [numeronym](https://en.wikipedia.org/wiki/Numeronym) and the most succinct/common representation of the word "accessibility" on the web. The basic idea is that there are 11 letters between the first and last letters: a-ccessibilit-y. Other common numeronyms are i18n (i-nternationalizatio-n) and l10n (l-ocalizatio-n).

#a11y is the most common hashtag you'll find online, and particularly great to [surface goings-on on Twitter](https://twitter.com/search?q=%23a11y&src=typd&lang=en).

In this post, "assistive technologies" are tools used by people with disabilities to use software/websites. AT is a broad spectrum of devices or software depending on the type of disability: [visual](http://webaim.org/articles/visual/), [auditory](http://webaim.org/articles/auditory/), [motor](http://webaim.org/articles/motor/) or [cognitive](http://webaim.org/articles/cognitive/). I'll typically abbreviate "assistive technologies" as AT.

## Paradigm shifts

I had a few "aha!" moments when I was learning about accessibility that I felt had huge impacts on how I thought about building websites. These included the accessibility tree, keyboard accessibility and how users of AT interact with websites.

### The accessibility tree
I had a seminal moment early on in my accessibility journey at [Beecher's Cheese](http://www.beechershandmadecheese.com/Locations/NewYork.aspx) after my first visit to the [A11YNYC](https://www.meetup.com/a11ynyc/) meetup. I probably said something that was very incorrect, at which point the person I was talking to asked me, "wait, do you understand the accessibility tree?"

The [accessibility tree](https://developers.google.com/web/fundamentals/accessibility/semantics-builtin/the-accessibility-tree) is a tree-based, internal representation of the UI that is exposed explicitly to AT. If you've ever used Chrome developer tools to examine the DOM tree the accessibility tree is similar in spirit. Browsers map your HTML into a tree-based structure of nodes that represent a **visual** display of information (the DOM tree). Browsers also map your HTML into a tree-based structure of nodes that represent a **semantic** display of information (the a11y tree).

"Semantics" is the key term here. The a11y tree is entirely about semantics. The DOM tree cares about what your HTML looks like. **The a11y tree cares about what your HTML means**.

AT are essentially robots that consume an accessibility tree. That's the key takeaway: AT don't look at rendered UI, and the interface between AT and computing interfaces is the accessibility tree.

Let's cover a trivial example of the implications of HTML semantics. Imagine a UI with the following "buttons" (currently styled via bootstrap):

<p data-height="265" data-theme-id="0" data-slug-hash="gGYXLo" data-default-tab="html,result" data-user="dxna" data-embed-version="2" data-pen-title="Buttons: span vs button" class="codepen">See the Pen <a href="https://codepen.io/dxna/pen/gGYXLo/">Buttons: span vs button</a> by Dan Na (<a href="https://codepen.io/dxna">@dxna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

Visually these buttons appear to be exactly the same: same color, font, border-radius, etc. If all you care about is what your HTML looks like (the DOM tree) then those HTML snippets are equivalent. But if you care about what the HTML means (the a11y tree), those HTML snippets are completely different.

Because CSS class names are arbitrary, AT can't know that your `btn` and `btn-primary` classes make a `<span>` or `<div>` appear like a button. If you use an actual `<button>` HTML element, you promote proper HTML semantics and increased usability for AT users.

Users of AT know that elements on a webpage are designed to perform specific behaviors -- buttons trigger actions, links redirect to content, headings designate topical hierarchy, etc. These assumed behaviors and semantic meanings are baked into HTML specifications, which is why, for example, `<h1>` tags are intended to precede `<h2>` tags. When web developers arbitrarily use HTML elements without regard for their semantic meanings and instead rely on visual treatments to prescribe meaning, this foundational understanding of how webpages work crumbles and usability for non-visual users crumbles with it.

Imagine a low vision or blind screen reader user. When the screen reader traverses the a11y tree, the `<button>` element above will be announced as a "button". The user can then make inferences about how to interact with the current page given that announcement. "Ah, this is a button, meaning it should perform an action." In contrast, a `<span>` or `<div>` styled to appear like a button do not express the same intention, and a screen reader may not even announce them at all.

When I understood the idea of the a11y tree I felt like understanding the accessibility implications of UI decisions no longer required a huge suspension of disbelief. Why do form labels need properly associated inputs? Because visually co-locating a label next to an input is not enough. Using the "[for](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)" attribute builds that semantic association between label and input. Why add "[alt](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)" attributes describing the contents of images? Because if you can't visually inspect an image, how else would you know its contents? (_Note: there's nuance to adding alt attributes to images. See ["Writing for all people: how to use alternative text well"](https://ux.shopify.com/writing-for-all-people-how-to-use-alternative-text-well-1205a18307a1) by Shopify UX._)

For a long time the a11y tree wasn't easy to visualize well. However, as a result of some amazing work by the Chrome team, you can even view the a11y tree in Chrome DevTools if you turn on an experimental flag.

First, turn on the DevTools experiment flag by navigating to `chrome://flags`:

<img class='bordered' src='/assets/img/2017-09-18/chrome_flags.png' alt='Turning on the Developer Tools experiments flag in Google Chrome'/>

Then, enable the "Accessibility Inspection" checkbox under the Experiments menu (use `SHIFT+CMD+P` to access the dynamic dropdown):

<div class='img-container'>
<img class='bordered' src='/assets/img/2017-09-18/chrome_experiments.gif' alt='Enabling the Accessibility Inspection checkbox in the chrome devtools experiments menu'/>
</div>

Let's look at some form inputs with labels of varying correctness and their names in the accessibility tree. As demoed by the following CodePen, the following three text inputs look identical:

<p data-height="265" data-theme-id="0" data-slug-hash="zExoEj" data-default-tab="html,result" data-user="dxna" data-embed-version="2" data-pen-title="Labels" class="codepen">See the Pen <a href="https://codepen.io/dxna/pen/zExoEj/">Labels</a> by Dan Na (<a href="https://codepen.io/dxna">@dxna</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

The "First name" label is properly associated to its input via the "for" attribute. Thus, when you focus the "First name" input, the accessible name comes from the label:

<div class='img-container'>
<img class='bordered' src='/assets/img/2017-09-18/labels_1.png' alt='Accessiblity tree for the first name input showing a proper accessible name, via the "for" attribute'/>
</div>

The "Middle name" label doesn't have a "for" attribute but is properly associated with its input via wrapping. Thus, when you focus the "Middle name" input, the accessible name comes from the label:

<div class='img-container'>
<img class='bordered' src='/assets/img/2017-09-18/labels_2.png' alt='Accessiblity tree for the middle name input showing a proper accessible name, via wrapping'/>
</div>

The "Last name" label is visually next to, but unassociated with, its input. Thus, when you focus the "Last name" input, there is no prevailing name in the accessibility tree:

<div class='img-container'>
<img class='bordered' src='/assets/img/2017-09-18/labels_3.png' alt='Accessiblity tree for the last name input showing no accessible name'/>
</div>

Again, unlike consuming an interface visually the accessibility tree can't make inferences based on location. Despite the fact that those three form fields appear properly constructed they're not. Associations and representations must be semantic and explicit.

My main point is that understanding the concept of the accessibility tree means that you don't need a disability to perceive how an interface is parsed by AT. Does each item have a representative name or label? Does your use of HTML elements match their intended purpose? (i.e. are you using LINKS to redirect to content and BUTTONS to perform actions?) If so, great! If not, the semantic representation of your interface might not make sense.

### Keyboard accessibility

Making your site fully keyboard accessible will go a **long** way towards making your site generally accessible. What I mean by "keyboard accessibility" is your ability to perform every action on the site without the use of a mouse.

This is consistent with how a lot of AT fundamentally work. From screen readers to [sticks, wands and switches](http://webaim.org/articles/motor/assistive#intro), traversing a webpage from beginning-to-end via many forms of AT is essentially traversing via keyboard focus.

Chances are the majority of the websites you visit on a daily basis are completely keyboard inaccessible. I'd encourage you to go to some of your favorite websites and try it yourself. Major considerations here include a visible keyboard focus indicator and the ability to get in and out of menus and modals. If you press `TAB` on your company's website, can you follow the keyboard focus throughout the page or does it get lost via [some errant `outline: 0` CSS](http://www.outlinenone.com/)?

Modals are particularly problematic. When you click a button to open a modal, does keyboard focus enter the modal content? Can you press the `ESCAPE` key to close the modal? When you do close it, does keyboard focus return to the element that triggered its opening?

There are also some particular behaviors around keyboard interactions. Did you know that `<button>` elements are triggered by default by both `SPACEBAR` and `ENTER` keypress? When you use `<span>` and `<div>` elements to create "buttons" this means you must add additional JS to attach event listeners for these keypresses (which is another reason to use the stock `<button>` element!)

Training every designer/developer at your company how to use a screen reader may be an unrealistic goal. But emphasizing building interfaces that are functional with a keyboard is completely doable and can preempt a lot of accessibility problems. Designers can easily include both `hover` and `focus` states within design comps, and you can make a visible focus outline mandatory within your UI.

### How do AT users interact with websites?
If you're like me, chances are you've never seen a user of AT interact with a website. It's an eye-opening experience and likely more intuitive than you think.

Think about how most sighted people consume webpages. Chances are they visually skim the page. When they're looking for a specific type of functionality their eyes dart around the page, looking for the "Add to cart" or "Sign in" button. When they're looking to simply understand the gist of an article they may scroll quickly, reading the headlines but skipping the details.

Here's what navigating via headline looks like in VoiceOver and Safari for this blog post:

<div class='img-container'>
<img class='bordered' src='/assets/img/2017-09-18/voiceover_headings.jpg' alt='The headings list for this blog post from VoiceOver on Mac OS X, using the web rotor.'/>
</div>

AT like screen readers enable users to iterate specific components of a page in a similar vein. Users will often iterate the headings only to get an idea of the page structure or drill down on a specific area, or iterate only the form elements to see what actions are available (like "Sign In" or "Add to Cart"). This effectively answers the question, "semantically, what does this page look like?" If your headings don't respect proper hierarchy (`<h1>`s before `<h2>`s before `<h3>`s... and no skipped levels) or you use `<span>`s in lieu of `<button>`s, these navigation methods are rendered useless. Yet another reason why proper semantics are huge.

## Changing culture

Changing a culture to care about accessibility is the number one thing people ask about, and for good reason -- it's the hardest part. Our team was lucky in that the company was very values aligned and we had a lot of buy-in from leaders and coworkers who wanted to build accessible products but didn't know where to start.

If you work at a place that lacks similar values alignment that's okay, as I still think there are some compelling business reasons to care about accessibility. But that does likely create an uphill battle. While I don't have a silver bullet here, I do have some considerations that I think are relevant.

### The business case

#### Legal
Legal liability around inaccessible websites is real. In 2008, [Target Corp settled a $6M class action lawsuit with the National Federation of the Blind](https://arstechnica.com/uncategorized/2008/08/target-to-pay-6-million-to-settle-site-accessibility-suit/) over its inaccessible shopping experience. Since then Target.com has made amazing strides to provide an accessible experience for online shoppers.

Organizations like National Federation of the Blind can sue companies as a very effective advocacy measure. And once that happens, frankly, you're not left with great options. Here's a headline you don't want across TechCrunch: "[Your company] countersues National Federation of the Blind."

For companies with a web presence in Europe, there is also an [increasing number of web accessibility regulations being set by European countries](http://webaim.org/articles/laws/world/europe). If you plan to internationalize your product, prepare to take a serious look at accessibility before you do so.

That being said, the risk of legal liability wrt accessibility is very difficult to quantify. Karl Groves [has a great blog post exploring this uncertainty](http://www.karlgroves.com/2011/12/08/reduction-of-legal-risk-as-accessibility-business-case/) that's worth a read.

#### SEO
Remember when I said this?

> AT are essentially robots that consume an accessibility tree.

AT remind me of another common robot that derives semantic meaning from markup: search engine crawlers.

When I was first introduced to HTML5 semantics years ago one of the compelling reasons to use an `<aside>` and `<article>` tag was for SEO reasons. By breaking up pages into semantic, component parts, Google could better understand my content and my SEO rating would improve.

While I'm not claiming that PageRank is a function of accessibly built pages, accessibility and SEO techniques have a lot of overlap. Proper semantic structure, meaningful and properly hierarchical heading outlines, images with alt attributes, etc. are both accessibility and SEO wins. Fix the accessibility of your site and get SEO improvements for free.

#### "How many people with disabilities use our site anyway?"
If your site is inaccessible, none. There's a strong chicken-and-egg problem here.

If your site is accessible, then that's probably dependent upon the nature of your product. But why preempt yourselves from a market of people, especially one which grows as the population ages?

This is a good segue into the next point...

### Can you hear from real users? (User research is amazing)
Does your company have forums or an email queue? Can you search it for key terms related to accessibility to see if any customers or members with disabilities have already actively contacted the company about the problems they're facing?

If so, find an email about the inaccessible features of a specific product and send it to that product team. I guarantee you they will care and immediately think of ways to fix the problems.

Does your company have a User Research (UR) team that conducts user research sessions? We did, and the team was incredible, and the sessions they conducted provided unparalled insight into user behaviors and expectations. If so, try to schedule an accessibility-focused UR session. If you thought emails were powerful, a video of a user with disabilities becoming stuck on inaccessible interfaces is even more so.

The goal of bringing in real user feedback is empathy and context. Sure, you can (and should) run training sessions around accessibility topics, but at its heart accessibility is a human issue affecting real people. The more you can make those people real to your organization, the more effective your evangelism efforts will be.

## Remediation strategies
Okay, enough of the theoretical stuff. Let's talk about actually identifying and fixing accessibility issues.

### Automation
The good news: you can automate the identification and remediation of some accessibility errors. There are a number of tools that will do something like scan a page and produce a report, but the one I prefer and will shout from the rooftops is [aXe from Deque Systems](https://www.deque.com/products/axe/).

aXe is a free, open-source accessibility utility that can be run via [Chrome/Firefox extension](https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd) or via a [core js library](https://github.com/dequelabs/axe-core). aXe was built with a [few simple design principles](https://github.com/dequelabs/axe-core#manifesto), the one I love most being "no false positives." aXe doesn't claim to identify every accessibility error under the sun (although it identifies a ton), but when it does report something as an error you can rest assured that it is true. As the timeless software adage goes, a flaky test is a worthless test.

<div class='img-container'>
<img class='bordered' src='/assets/img/2017-09-18/axe_espn.png' alt='Screenshot of the output of running the aXe chrome extension over espn.com'/>
</div>

An aXe report will display errors and their counts, their location in the DOM, meaningful description/context about the error and suggest a fix. It will also tag errors with their related WCAG 2.0 success criteria (in this case, [guideline 1.4.3](https://www.w3.org/TR/WCAG20/#visual-audio-contrast)) and WCAG 2.0 compliance level (in this case [WCAG 2.0 AA](https://www.w3.org/TR/WCAG20/#conformance-reqs)).

I consider the aXe Chrome extension a must-install for those who are serious about accessibility. Developers can also couple the axe-core library with something like PhantomJS to potentially create their own internal accessibility error monitoring service.

### Manual accessibility review
Some less good news: unlike some other technical problem spaces, accessibility remediation is difficult to fully automate. In fact, if you talk to people who have been doing this for a while, they'd argue that only around 30% of accessibility problems can be automatically identified and remedied.

The reason is because many accessibility problems are UX failures. For example, your site design wasn't conceived with keyboard interaction in mind, or a common user flow doesn't make sense for a non-sighted experience. We're no longer talking about straightforward and deterministic errors like disassociated form inputs and labels, but rather fundamental UX problems with no simple fixes.

This is why a manual accessibility review process was still a core part of the accessibility effort at many of the other companies we spoke to. The most effective teams tied accessibility review to product milestones/launches, even going so far in some places as to block product launches until they received accessibility review (enforced at the VP level!). While that level of organizational buy-in may not be available to everyone, there were some tenets we tried to enforce within our own review process:

1. **Set clear expectations.** Our team would provide a keyboard, aXe and screen-reader review. We'd file tickets against your team's JIRA backlog, consistent with parameters that the eng or product manager specified in a Google form they'd complete before the review began. We'd deliver accessibility errors as bug tickets within a maximum of two weeks, and the tickets themselves would contain information to identify the problem and its suggested fix. We would include a screenshot or screencast as necessary.
2. **Celebrate the efforts of those who provide fixes.** Our team sent out a monthly email to a voluntary, company-wide listserv outlining the work we completed that month. We'd use that email to celebrate teams and coworkers who made accessibility fixes, with examples of how those fixes impacted their products.
3. **Tie accessibility review into meaningful dates.** Is there a product launch calendar? Do product teams request QA at a set time before launch? That's a great way to know when to reach out to specific teams about accessibility review. If teams have a product launch checklist (QA/performance/etc.), get on that checklist.

### Bake accessibility into your UI/component library/styleguide

Does your company have a UI/component library/styleguide? Is that library a source of truth for all current and future UI development?

If so, prioritize fixing the accessibility of your components. Baking accessibility into a shared component library is one of the highest leverage activities your team can perform. It's the best way to future-proof all new development with a baseline level of accessibility.

### "Accessibility is solved at the design stage"

The first time our team attended the [CSUN Assistive Technology Conference](http://www.csun.edu/cod/conference/2017/sessions/), the biggest accessibility conference in the world, one phrase we heard over and over again in sessions was "accessibility is solved at the design stage."

The later in the product development lifecycle accessibility concerns are surfaced the harder fixing them becomes. It's definitely more expensive and sometimes impossible. The worst case scenario for any team is to spend months designing, coding and validating a product design only to find that it's a fundamentally broken experience for AT users. If you can equip your designers to know what considerations to keep in mind before coding even begins -- keyboard accessibility, color contrast, hover and focus states, etc. -- it will go a long way towards stopping accessibility problems before they start.

## Quick wins / where to start
As I said before, approaching accessibility can seem like an insurmountable, intractable problem. Before we hired Cameron (the SME), Kristyn and I weren't sure which paths to pursue. The problem space felt very unbounded, so I know how it feels to not know where to start. 

*Side note: if you can hire a senior-level IC with deep accessibility domain expertise I strongly encourage you to do so. It's great to have strategic direction validated by experience.*

Instead of jumping straight into automated solutions or even manual accessibility review, I suggest first familiarizing yourself with WCAG 2.0, getting plugged into a local #a11y community, and implementing a few quick wins on your product to (1) surface accessibility to the rest of your organization and (2) have immediate impact on visitors to your website who use AT.

### Familiarize yourself with WCAG 2.0

WCAG 2.0 is the abbreviation for the [Web Content Accessibility Guidelines 2.0](https://www.w3.org/WAI/intro/wcag). It’s a series of guidelines, based on four core principles of [Perceivable](https://www.w3.org/WAI/WCAG20/quickref/#principle1), [Operable](https://www.w3.org/WAI/WCAG20/quickref/#principle2), [Understandable](https://www.w3.org/WAI/WCAG20/quickref/#principle1) and [Robust](https://www.w3.org/WAI/WCAG20/quickref/#principle4), on how to make web content more accessible to people with disabilities. It also includes success criteria to meet different levels of conformance (A, AA and AAA). Most websites that take accessibility seriously attempt to meet conformance level AA.

WCAG 2.0 is extensive -- see this "[WCAG 2.0 quick reference](https://www.w3.org/WAI/WCAG20/quickref/#keyboard-operation)" -- so by "familiarize" I don't necessarily mean "memorize." The value in reading over the guidelines a few times is to [develop a sense of smell](http://blog.danielna.com/2017/03/24/my-management-philosophy.html#on-our-work-as-a-team) around accessibility. It's the best starting point for building your intuition on what to look for and what might be a problem.

### Get plugged into the #a11y community
This is a hard road to go alone, especially when there are so many awesome people who care about this work. The most important thing I did was start attending the [A11YNYC meetup](https://www.meetup.com/a11ynyc/). What I like most about A11YNYC is that it's *not* a tech meetup, it's an accessibility meetup. Not everyone works in tech and not every presentation is tech-focused. Many attendees are users of AT. Hearing from them directly proved to be invaluable for developing my own empathy and understanding around the obstacles they were facing.

If you can swing it, attend the [CSUN conference](http://www.csun.edu/cod/conference/2017/sessions/). CSUN is a gamechanger. There are speakers and sessions about every accessibility-related topic under the sun -- a tech track, a legal track, an education track, etc. -- and many of the biggest names in web/mobile accessibility attend and speak. The relationships we formed with teams at companies like LinkedIn and eBay were particularly valuable, as they both have super high-performing and seasoned accessibility teams. Those teams provided a glimpse into more mature processes than ours and gave us goals/milestones to shoot for.

The #a11y community is honestly one of the kindest and most generous tech communities I've ever encountered. Company lines melt into the background of our greater shared goals. If you're willing to put in the work, countless more experienced people will be willing to help. This blog post is a reflection of that ethos.

### Add a "Skip to content" link
A "Skip to Content" link is visible only via keyboard focus and should be one of the first elements in the DOM. The idea behind a "Skip to Content" link is that keyboard-only or AT users can use it to move focus to the main container on the page, bypassing any global header or navigation menus.

Here's a look at the "Skip to Content" and "Skip to Navigation" links on the homepage of the New York Times:

<div class='img-container'>
<img class='bordered' src='/assets/img/2017-09-18/nytimes_skiptocontent.gif' alt='Demoing the skip to content link on nytimes.com'/>
</div>

WebAIM has a [great article on creating "Skip to Content" links](http://webaim.org/techniques/skipnav/).

### Fix your heading outlines
In the "[How do AT users interact with websites?](#how-do-at-users-interact-with-websites)" section, I mentioned how a common navigation pattern for AT users is to navigate page headings. As a result it's critically important to make sure that your page headings are (1) meaningful and (2) sequential. Don't skip levels.

Meaningful and sequential headings are also a strong forcing function for good design. Well designed interfaces display a clear and meaningful information hierarchy.

A common mistake is to use heading tags as style/font-size rather than as a designation of page hierarchy. In simpler language, don't use an `<h1>` when you want bigger font; use CSS for font-sizes. Use an `<h1>` to designate the most important and highest level heading on your page. If you think of your page content as a book, the headings are the table of contents. The `<h1>` is the title.

We took advantage of a special toolbar that only existed in dev environments that allowed engineers at the company to include special utilities or diagnostic tools. We added an accessibility-focused section within this toolbar with a set of JS widgets that we grew over time. One such widget visualized the page heading hierarchy in a small box at the top of the screen. This was an easy way for developers to know if their page hierarchies were an accurate representation of page content and sequential.

If your design doesn't allow for visible headings where they should be, a simple way to add headings into the a11y tree but not alter the visual design is to [use a class to represent invisible content](http://webaim.org/techniques/css/invisiblecontent/). I learned about this technique from an awesome blog post by the NYT -- "[Improving Article Accessibility](https://open.blogs.nytimes.com/2014/06/24/improving-article-accessibility/)." Look specifically for the implementation of the `.visually-hidden` class in that article.

### Fix your forms
Run aXe on your forms.

Forms are the backbone of the interactivity of your product. Default to using stock HTML inputs whenever possible (rather than re-creating more complicated form inputs in JS) and make sure that inputs are properly associated with labels. Placeholder text on inputs is an insufficient replacement for a label, but using the invisible content trick above you can visually hide labels if they conflict with your design.

## Everything else
An assortment of thoughts on topics that didn't fit into categories above.

### What's the deal with ARIA?
ARIA stands for Accessible Rich Internet Applications, and it "defines ways to make Web content and Web applications (especially those developed with Ajax and JavaScript) more accessible to people with disabilities. For example, ARIA enables accessible navigation landmarks, JavaScript widgets, form hints and error messages, live content updates, and more." [(via MDN)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)

In layman's terms, ARIA is a set of attributes you can place on HTML tags to directly manipulate the accessibility tree. I consider implementing ARIA an advanced topic that requires the knowledge of how to use a screen reader. Different screen readers can also treat the same ARIA implementations differently.

There's been a lot already said about ARIA, and it is a very deep rabbit hole. I'm also by no means an ARIA expert. I will say this: ARIA can provide quick and easy accessibility wins in the best case [(see: landmarks)](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page), and in the worst case be complicit in completely over-architecting JS widgets that should really just be default HTML inputs (like very complex JS-driven dropdowns). For a good introduction of what ARIA can look like in the wild, check out this post from [@heydonworks](https://twitter.com/heydonworks): [Practical ARIA Examples](http://heydonworks.com/practical_aria_examples/). I also highly recommend the eBay accessibility styleguide, [eBay MIND Patterns](https://ebay.gitbooks.io/mindpatterns/content/).

If you do decide to learn how to use ARIA, the [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices-1.1/) was the resource we used to dictate normative ARIA-widget behavior. You'll want to use it in conjunction with documentation like [supported states and properties](https://www.w3.org/TR/wai-aria/states_and_properties). Concepts to grok before implementing the specifications in these widgets include [keyboard navigation within components](https://www.w3.org/TR/wai-aria-practices-1.1/#kbd_general_within) and [intentionally hiding semantics from the a11y tree using role=presentation](https://www.w3.org/TR/wai-aria-practices-1.1/#presentation_role).

### What's the deal with screen readers?
Screen readers are intended to be used with specific browsers.

* [JAWS](http://www.freedomscientific.com/Products/Blindness/JAWS) is proprietary screen reading software developed by Freedom Scientific and historically the market leader/most widely used. It's expensive, with licenses costing $1000+. It should be used with Internet Explorer. _Fun fact, MS Edge is technically not Internet Explorer, a lesson I learned after one particularly frustrating afternoon in the office._
* [NVDA](https://www.nvaccess.org/) is free and open source, and initially developed by two blind screen reader users. Colloquially I've been told it's considered to be the most standards compliant of the screen readers. It should be used with Firefox.
* [VoiceOver](https://www.apple.com/accessibility/mac/vision/) is free and ships with OS X/iOS. It should be used with desktop and mobile Safari. Apple as an organization is exceptional at including accessibility considerations into their OS/default UI developer kits, so the overwhelming majority of mobile users use VoiceOver on iPhones. It works very well.

An obvious question is "what's the current market share of each screen reader?" That's a harder question to answer than you'd think. Unlike web browsers, screen readers can't be sniffed via mechanisms like HTTP headers. Screen readers operate at the OS-level, not the browser level. Beyond that, screen readers can't be sniffed as a privacy concern. Screen reader users have the right to the same experiences that non-screen reader users have, and sniffing AT would lend itself to serving different experiences.

Fortunately there is a good and voluntary proxy for screen reader usage: [the WebAIM screen reader survey](http://webaim.org/projects/screenreadersurvey6/). While that 2015 survey is not a sample of every screen reader user in the world, the 2515 respondents do represent a self-selective group of highly engaged users.

> For respondents that report blindness, 38.9% use JAWS, 26.5% use Window-Eyes, 16.9% use NVDA, 8.7% use VoiceOver, and 4.6% use ZoomText. For respondents that report having low vision, 53.5% use ZoomText, 16.5% use JAWS, 12.2% use Window-Eyes, 8.7% use NVDA, and 4.6% use VoiceOver. ZoomText was also more commonly used by users with auditory, motor, and cognitive disabilities than by users with blindness.

Window-Eyes has since been discontinued and the [official website has instructions to migrate to JAWS](http://www.gwmicro.com/).

We tested across JAWS, NVDA and VoiceOver, being careful to test within their intended browsers. The Chrome team develops its own screen reader, [ChromeVox](http://www.chromevox.com/), but due to its lack of adoption we didn't use it.

The important caveat to non-native AT users testing with AT is to know that you'll likely never use it in the same way as a native user. Simple testing is fine -- "how does this element sound when I traverse to it" -- but it's critically important to check your assumptions of AT use with real users, ideally through mechanisms like user research sessions.

### What are other organizational accessibility wins to consider?

#### Real-time captioning
Have you ever been to a meeting or conference with real-time captioning? It is incredible to watch. Real-time captioning is what it sounds like -- someone types up the conversation, in real-time, and it's projected on screen to all conference attendees. It's a win for both inclusivity and clarity.

One good way to make accessibility more prominent within your organization is to advocate for captioning (aka CART, which stands for Communication Access Real-time Translation) services at internal/external meetings and conferences. Two amazing stenographers I've seen in person in NYC are [Mirabai Knight](https://stenoknight.com/) and [Stanley Sakai](http://superlativerealtime.com/).

#### Video captions
Does your organization produce video? Add captions.

#### Invite guest speakers
Invite guest speakers to speak at your company for lunch-n-learns. I saw [Jake Voytko](https://www.bitlog.com/) (now an Etsy engineer!) give his amazing "[I am colorblind, and you can too!](https://www.bitlog.com/index.php/2015/10/21/transcript-of-i-am-colorblind-and-you-can-too/)" talk at A11YNYC. Immediately afterwards I invited him to come speak at the company, which turned out to be an awesome way to introduce coworkers to the concept of color-blindness.

As a related aside, if you tweet a picture at Jake's [@JakeWouldSee](https://twitter.com/jakewouldsee) twitter bot, it'll respond with a version of the photo how he'd see it, given his color blindness. It's amazing.

If you want your mind blown `CMD+F` his blog post for the word "sushi."

### Tools and resources we actually used
* Communication
  * [a11y-slack](https://web-a11y.herokuapp.com/): A slack room with all of the heavy-hitters in the web accessibility world. A great, inviting place to ask questions and learn.
* Accessibility tools
  * [aXe](https://www.deque.com/products/axe/): My favorite accessibility testing tool. The browser extension is wonderful.
  * [AccessLint](https://www.accesslint.com/): AccessLint is a GitHub App that finds accessibility issues in your pull requests(!!). The lead developer is Cameron Cundiff, my ex-teammate and all-around awesome person/engineer.
  * [WebAIM Color Contrast Checker](http://webaim.org/resources/contrastchecker/): Make sure your colors meet minimum WCAG 2.0 contrast requirements.
  * [Sketch Color Contrast Analyzer](https://github.com/getflourish/Sketch-Color-Contrast-Analyser): Most of our designers used Sketch. This was a plugin to analyze color contrast.
  * [Adobe Photoshop color blindness simulation](https://www.adobe.com/accessibility/products/photoshop.html): Instructions on how to simulate various modes of color-blindness in Photoshop. This functionality comes stock.
  * [SimDaltonism](https://itunes.apple.com/us/app/sim-daltonism/id693112260?mt=12): Free Mac app from the Mac App Store that allows you to simulate various color blindness modes on your screen.
* Tools that help with accessibility screencasts
  * [keycastr](https://github.com/keycastr/keycastr): Free/open source keystroke visualizer. Display keypresses on screen, which allows co-workers to emulate your keystrokes to re-produce accessibility errors.
  * [Screenflow](https://www.telestream.net/screenflow/overview.htm): Capture video screencasts with system audio. Coupled with keycastr, you can show co-workers what commands you're pressing and how screen readers respond. $130.
  * [GIPHY Capture](https://giphy.com/apps/giphycapture): Similar to screen flow but for when animated gifs suffice. For a long time I used [LICEcap](https://www.cockos.com/licecap/), but I find GIPHY Capture to be easier to use and have more options regarding gif quality.
* Meet like-minded people
  * [A11YNYC](https://www.meetup.com/a11ynyc/): The NYC accessibility meetup.
  * [A11yCamps](http://www.a11ycamp.org/find-an-a11ycamp/): A11yCamps are participant-driven events about web and software accessibility, with presentations, demos and interaction by and for A11yCamp participants. They're regional and great!
  * [CSUN Assistive Technology Conference](http://www.csun.edu/cod/conference/2017/sessions/): The world's largest accessibility conference in San Diego, CA. The accessibility mothership. Go, learn, network. If you can go to one conference a year, make it this one. For insight into what this conference is like, [read this recap by Nicholas Zakas from 2010](https://www.nczonline.net/blog/2010/03/30/csun-conference-2010/).
* Introductory online resources
  * [WebAIM](http://webaim.org/): A lot of great introductory/overview resources around accessibility topics.
  * [MDN Web Docs: Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility): Resources via the Mozilla Developer Network.
  * [Web Accessibility by Google on Udacity](https://www.udacity.com/course/web-accessibility--ud891): Free online video course taught by accessibility engineers at Google.
* Official documentation
  * [WCAG 2.0 Quick Reference](https://www.w3.org/WAI/WCAG20/quickref/)
  * [ARIA in HTML](https://w3c.github.io/html-aria/): Background on how ARIA and HTML intersect.
  * [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices-1.1/): The functional source of truth when building accessible JS widgets.
* More specific online resources (and things I bookmarked)
  * [eBay MIND Patterns](https://ebay.gitbooks.io/mindpatterns/content/): The eBay accessibility team does really incredible work. They're also great people. This is their accessibility component styleguide, and IMO the best such resource on the web.
  * [How I Audit a Website for Accessibility by Marcy Sutton](https://marcysutton.com/how-i-audit-a-website-for-accessibility/)
  * [Ryan Florence's gist on Accessible Modals](https://gist.github.com/ryanflorence/fd7e987c832cc4efaa56)
  * [How Our CSS Framework Helps Enforce Accessibility from the eBay tech blog](http://www.ebaytechblog.com/2015/11/04/how-our-css-framework-helps-enforce-accessibility/)
  * [Shopify's medium post series on Accessibility](https://ux.shopify.com/make-commerce-better-for-everyone-b96f0621ddf3#.qkhbxkncz): Covers a bunch of great topics: color contrast, accessible pricing, alt text, semantics, data tables, real user testing and culture.
  * [Color Contrast and Why You Should Rethink It from SmashingMag](https://www.smashingmagazine.com/2014/10/color-contrast-tips-and-tools-for-accessibility/)
  * [Accessible SVGs from css-tricks](https://css-tricks.com/accessible-svgs/)
  * [Accessible Mega Menu from Adobe](https://adobe-accessibility.github.io/Accessible-Mega-Menu/)
  * [Danger! Testing Accessibility with real people by Leonie Watson](https://medium.theuxblog.com/danger-testing-accessibility-with-real-people-4515f72db648)
  * [!!Con2016 - How I Code and Use a Computer at 1,000 WPM!! by Sina Bahram](https://www.youtube.com/watch?v=G1r55efei5c): Amazing conference talk from bangbangcon 2016.


