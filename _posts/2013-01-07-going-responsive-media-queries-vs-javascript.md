---
layout: post
title: Going Responsive - Media Queries (CSS) vs. JavaScript
subtitle: Now accommodating desktop, 7" tablet, and mobile browsers.
tags: text
redirect_from: "/2013/01/07/going-responsive-media-queries-vs-javascript.html"
---

I spent a few hours tonight changing things around here, most notably incorporating <a href="https://www.google.com/webfonts" title="Google Web Fonts" target="_blank">Google Web Fonts</a> and making the site responsive using <a href="http://mobile.smashingmagazine.com/2010/07/19/how-to-use-css3-media-queries-to-create-a-mobile-version-of-your-website/" title="Media Queries | Smashingmag" target="_blank">CSS media queries</a>.  That means it'll render differently on desktop, tablet, and mobile.  Try it yourself by resizing your browser window.

This was the first time I've used media queries.  I've worked on a <a href="http://www.coca-colacompany.com" title="Coca-Cola Company" target="_blank">responsive design at work powered by JavaScript</a>, meaning we'd determine the page dimensions via JS and swap out things like JS functions, stylesheets, etc. as necessary. I think my takeaways are:

1. If you have a JS-heavy site that needs to fire different functions based on device/layout, use something like <a href="http://adapt.960.gs/" title="Adapt.js" target="_blank">adapt.js</a> and its callbacks.
1. If you just want to degrade structure/styles simply without a lot of JS changes, use media queries.

When I refer to "JS-heavy site" I mean a site with a lot of functional differences between screen sizes: interactions, forms, AJAX, i.e. things that can't be handled by a simple hiding/showing of elements.  A site like this blog is probably the ideal candidate for media queries, or most blogs in general with a generally redundant page structure. 

If I had to guess most non-massive websites probably fall within category #2.
