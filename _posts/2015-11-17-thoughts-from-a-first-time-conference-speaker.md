---
layout: post
title: Thoughts from a First Time Conference Speaker
subtitle: On the road to post-talk euphoria
tags: text
---

I gave my first conference talk this past week at <a href="http://sassconf.com/" target="_blank">SassConf 2015</a> in Austin, Texas.  It
was a full 40 minute talk entitled "Transitioning to Sass at Scale," which chronicled transitioning all of Etsy's CSS to Sass in October 2014. 
It was awesome to have the opportunity to share about the most complex and rewarding project of my career thus far. 
In February I wrote a really long blog post on Etsy's engineering blog about it:
<a href="https://codeascraft.com/2015/02/02/transitioning-to-scss-at-scale/" target="_blank">Transitioning to SCSS at Scale</a>.

I've spoken publicly before, mostly in the context of <a href="http://www.cheekswab.org" target="_blank">Cheekswab</a>, but found preparing a tech conference talk
a different and interesting experience. I wrote down thoughts and insights I encountered during the process of creating 
my slides and iterating on my presentation.  Looking at them now they're less
about the mental or emotional aspects of speaking, nor are they a step-by-step
walkthrough of how to prepare a talk.  <a href="http://speaking.io/" target="_blank">Luckily 
those topics have been written about extensively.</a>

To see my annotated slides, see my <a href="http://talks.danielna.com/sassconf-2015/" target="_blank">talk details page</a>.

The notes below aren't chronological and I'm only separating them into categories
for the purposes of this blog post.  Writing them down was completely stream of consciousness.

<div class="separator">&raquo;&raquo;&raquo;&laquo;&laquo;&laquo;</div>

## SassConf
* SassConf was unique in that we had talk mentorship, meaning we were scheduled to meet semi-regularly
with someone who has speaking experience. I was fortunate that my mentor, <a href="https://twitter.com/elyseholladay" target="_blank">Elyse Holladay</a>, was one of the organizers of the conference and a conference slide savant.  There are a lot of finer detail-type things that were unintuitive to me as someone who was doing this the first time (which I talk about below). Her feedback on my slide content was really invaluable.
* I'd be legitimately surprised to find a more friendly, inclusive and diverse tech community than those that are involved with Sass. I've been to a good number of conferences focusing on different types of tech and SassConf always stands out with respect to how actually real-life diverse it feels.

## Content
* I find preparing a presentation more akin to essay writing than musical performance.  The delivery of your talk is definitely important, but excellent delivery of poor content is a bad presentation.  Even if you're not Steve Jobs, people who are genuinely interested in learning something new will see through your moments of ineloquence to the meat of your content.
* Only when you start going through the talk in full will you realize where your notes or slides are deficient.
* A couple weeks before give a shitty, cursory version of your not-done talk to a group of people.  This will help you build confidence that you're not lacking in core content (as opposed to polish).
* Present to a few friends who don't work at your company.  There's a lot of embedded vernacular in workplaces that is easy to take for granted because you work there.  When I mentioned X at Etsy, which every Etsian knows about, the reality was that nobody else knew what I was talking about. Because X has a fancy name it seems as if it's a detail that is important to focus on.  Avoid those company-embedded words entirely if you can, even if your technical precision suffers for it.
    * **Example 1:** Developers at Etsy do all of their work on virtual machines, which I originally stated in my slides.  But it's not an important detail, and if you don't know what a virtual machine is it may sound like that's a critical, complicated thing. At Elyse's suggestion I changed that wording to "local development environments" and my presentation was better for it.
    * **Example 2:** Our internal chat at work is via IRC. It completely doesn't matter if you know what IRC is. So instead of referring to "IRC," I refer to "chat".
* Of course the safe usage of technical terminology varies by audience. But I think it's an important consideration that flies in the face of the natural desire to go on stage and focus on selling how smart or technically savvy you are. Optimizing for audience comprehension is always the better decision.
* Initially I thought this talk would be more a talk about process of solving a specific problem and less a story that necessitated a lot of context.  What I mean is, a talk entitled "How to tie your shoes" doesn't seem like it needs much of a backstory; you just start walking through a step-by-step process. 

    But there's context to solving engineering problems, and adding that context -- that CSS exists on every page and making wide sweeping changes to our CSS codebase was scary because our members/sellers depend on us for their income -- made my talk much stronger.

## Slides
* Slides take a lot longer to prepare than you'd think, especially for a full 40 minute talk.  Mine took about 3 weeks.
* The easiest way to give presentations (and how people typically do it in grade school or for presentations they don't care about) is to dump every piece of text on a slide.  It is non-trivially hard to be intentionally non-verbose on slides, because it causes you to focus on what phrases are important, as well as sequencing and delivery.
* People will focus on numbers in slides even if they're not that important.  I had slides about Etsy metrics -- 21.7M active buyers, 1.5M active sellers, and $1.93B in sales in 2014 -- which I only had for the purpose of explaining that our site gets a lot of traffic.  Originally I had those numbers all on one slide until Elyse suggested transitioning through them quickly because otherwise they seem important to know.  I thought that was incredibly insightful.
* For slides that encompass a major takeaway, avoid slides that have one word on its own line. 

    This slide is hard to read:

    <pre style="display: block; width: 100%;">THIS IS THE TAKEAWAY FROM THIS
SLIDE.</pre>

    This is better:

    <pre style="display: block; width: 100%;">THIS IS THE TAKEAWAY
FROM THIS SLIDE.</pre>

    Again, insights, courtesy of Elyse.
* As a general truth that I've run across, if your notes for a single slide are very long -- several paragraphs -- chances are there's a natural transition somewhere to break things up into multiple slides.

## Speaking
* I prescribe to the <a href="http://blogs.ft.com/the-world/2010/02/the-secrets-of-malcolm-gladwell/" target="_blank">Malcolm Gladwell strategy</a> of presentation preparation: I practice enough times until it's effectively memorized.  I'll write down key phrases into my speaker notes that I want to make sure I hit word for word, and I'll improvise and add color in the moment.  But the practice/memorization is multi-purposed:
    1. Practice susses out logical holes in my presentation;
    2. It makes me feel more confident about my talk;
    3. It lets me go into mental autopilot when I'm on stage; and
    4. It appears more natural because I can improvise when I feel like it and then return to my internal script.

    Some people offer the advice of "just have sparse notes and speak in the moment," but personally that sounds to me like the opportunity for rambling that I can't get back from.
* The week before practice for polish and timing.
* If you're going to be funny care about the timing of your jokes. Don't show the punchline before giving the punchline.
* I avoid coffee on days I have to talk in front of people.  It can make me feel jittery and/or give me nerves-induced stomach problems.
* Use your transition slides to take a drink of water. 40 minutes is a long time to talk while "on", and while practicing I experienced a legitimate dry mouth around the 30 minute mark.  My full-page gif slides were a good opportunity for water and to generally catch a breath.
* Scheduling a conference is hard. Respect your time allotment as a proxy for respecting both the conference organizers and the attendees.
* Be the speaker you want to hear.  Show personality, practice, and care about the quality of your content. Half-assed, hastily put together presentations are self evident and disrespectful of the people who spend the time and money to attend the conference.

## Everything else
* Don't upgrade your system or presentation applications before your talk. Dealing with different versions of Keynote is fraught with sadness.
* Don't expect conference wifi to be any good (wifi with a lot of people is actually a really hard problem), so any demos that rely on connectivity might necessitate an unconnected analog.
* Make sure your slides project properly onto the screen before your talk.  It's worth purchasing VGA/HDMI-to-whatever-port-your-computer-uses adapters before you go.
* I really appreciate the positive feedback I received after my talk, and it was especially encouraging as a first time speaker. Ive heard horror stories from coworkers about people immediately approaching them after a talk to tell them every minute detail about where they were wrong, which is incredibly lame and unfortunate.  I'm cool with getting things wrong, but in a be-a-good-human-sense immediately after I speak is not the most appropriate time to point out those issues.
* It's worthwhile to create a page that includes your slides and links to things you spoke about in your slides, as well as any other things that are holistically valuable to mention.  This page also has the benefits of chronicling your conference talks in a single place, just in case talking at conferences is something you're interested in continuing.
* SassConf wasn't able to record the talks this year so I updated fully annotated slides to my talk page. I've seen some other speakers do that in the past and found it helpful as an outsider. Assuming they're exhaustive, I find annotated slides even more helpful than a recording.
* Turns out uploading slides as a PDF to SpeakerDeck without a ".pdf" extension can result in severely obscured colors.  Don't forget the file extension and save yourself some grief.
