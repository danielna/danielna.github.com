---
layout: post
title: Building a System for Front-end Translations
subtitle: Posted to the Squarespace engineering blog
tags: text
---

> Blog post link: [Building a System for Front-End Translations](https://engineering.squarespace.com/blog/2018/building-a-system-for-front-end-translations)
on [engineering.squarespace.com](https://engineering.squarespace.com)

I joined Squarespace in October 2017 as a senior software engineer on the Interface
Architecture team, which is the team that oversees Squarespace's frontend infrastructure.
When I joined the team they were in the middle of a multi-year effort to internationalize
Squarespace's huge frontend codebase. This was no simple task; there were over
480,000 lines of code across 7,000 .js/.jsx files, many of which hadn't been
modified in years.

As a new hire I was fortunate to be able to hit the ground running and contribute
to the internationalization initiative immediately. Eventually I spearheaded the
re-architecture of the system responsible for translation extraction and transport
into a more reliable system we dubbed the "Unified Translation Workflow."

All in all creating the frontend translation build system was a really fun and
rewarding project, full of the types of challenges and lessons that make me love
engineering. I wrote a [blog post](https://engineering.squarespace.com/blog/2018/building-a-system-for-front-end-translations)
for the Squarespace engineering blog sharing some our lessons learned about both
internationalization and systems design.

Enjoy!
