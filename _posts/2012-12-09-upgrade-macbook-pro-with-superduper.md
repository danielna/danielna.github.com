---
layout: post
title: Upgrading a Macbook Pro SSD with SuperDuper!
subtitle: The single biggest performance upgrade to any laptop.
tags: text
redirect_from: "/2012/12/09/upgrade-macbook-pro-with-superduper.html"
---

I figure this might help someone, if the google desires it so.

When I first bought my current MBP in early 2012 (13” unibody) I bought it with base specs.  The Apple upcharge on upgrading individual components being what it is, it was significantly cheaper to buy the MBP with a 320GB HD and 4GB RAM and upgrade everything myself. A <a target="_blank" href="http://www.amazon.com/gp/product/B004W2JKZI/ref=as_li_ss_tl?ie=UTF8&amp;camp=1789&amp;creative=390957&amp;creativeASIN=B004W2JKZI&amp;linkCode=as2&amp;tag=musings01b1-20">128GB SSD</a><img width="1" height="1" src="http://www.assoc-amazon.com/e/ir?t=musings01b1-20&amp;l=as2&amp;o=1&amp;a=B004W2JKZI" class="vomugjkpdjezjgmxstwf fafjirfvzezcugjzjnds" alt=""> and <a target="_blank" href="http://www.amazon.com/gp/product/B003DZJQQI/ref=as_li_ss_tl?ie=UTF8&amp;camp=1789&amp;creative=390957&amp;creativeASIN=B003DZJQQI&amp;linkCode=as2&amp;tag=musings01b1-20">8GB RAM</a><img width="1" height="1" src="http://www.assoc-amazon.com/e/ir?t=musings01b1-20&amp;l=as2&amp;o=1&amp;a=B003DZJQQI" class="vomugjkpdjezjgmxstwf fafjirfvzezcugjzjnds" alt=""> later (which is <em>much</em> cheaper now than it was then), my laptop was a freaking workhorse. The single biggest upgrade in performance was, by far, the SSD.

I couldn’t convince myself to spring for the 256GB drive then, mostly because the price for the drive was around $450. Needless to say, prices have dropped. <a target="_blank" href="http://www.amazon.com/gp/product/B004W2JL2A/ref=as_li_ss_tl?ie=UTF8&amp;camp=1789&amp;creative=390957&amp;creativeASIN=B004W2JL2A&amp;linkCode=as2&amp;tag=musings01b1-20">A lot.</a><img width="1" height="1" src="http://www.assoc-amazon.com/e/ir?t=musings01b1-20&amp;l=as2&amp;o=1&amp;a=B004W2JL2A" class="vomugjkpdjezjgmxstwf fafjirfvzezcugjzjnds" alt=""> With 50GB of music taking a big chunk of my hard drive space, I was getting tired of having to move media off to external drives. I decided recently that it was time to upgrade.

I took a long, hard look at the <a target="_blank" title="Optibay" href="http://www.mcetech.com/optibay/">Optibay</a>, which allows users to install a hard drive into their optical bays. In fact, I actually went so far as to order one, open up my laptop and attempt to install the thing. I became quickly annoyed that the published instructions did not have a schematic that closely matched the internals of my own computer, in addition to the required removal of a number of tiny screws that ran the risk of falling into the depths of my laptop forever. It was also unclear to me exactly how battery consumption would be affected by continually powering a second drive, which had the potential to derail my semi-frequent coffee shop sessions. Ultimately I sold the Optibay off to a friend who had better luck with the installation.

Here’s what I did:

<ol>
    <li>Purchased a <a target="_blank" href="http://www.amazon.com/gp/product/B004W2JL2A/ref=as_li_ss_tl?ie=UTF8&amp;camp=1789&amp;creative=390957&amp;creativeASIN=B004W2JL2A&amp;linkCode=as2&amp;tag=musings01b1-20">256GB Crucial M4 SSD</a><img width="1" height="1" src="http://www.assoc-amazon.com/e/ir?t=musings01b1-20&amp;l=as2&amp;o=1&amp;a=B004W2JL2A" class="vomugjkpdjezjgmxstwf fafjirfvzezcugjzjnds" alt=""> from Amazon;</li>
    <li>Downloaded <a target="_blank" title="SuperDuper!" href="http://www.shirt-pocket.com/SuperDuper/SuperDuperDescription.html">SuperDuper!</a>, a program for Mac that allows you to make an exact, bootable copy of your drive to an external disk;</li>
    <li>Used a <a target="_blank" href="http://www.amazon.com/gp/product/B002JQNXZC/ref=as_li_ss_tl?ie=UTF8&amp;camp=1789&amp;creative=390957&amp;creativeASIN=B002JQNXZC&amp;linkCode=as2&amp;tag=musings01b1-20">2.5” SATA to USB 2.0 HD Enclosure</a><img width="1" height="1" src="http://www.assoc-amazon.com/e/ir?t=musings01b1-20&amp;l=as2&amp;o=1&amp;a=B002JQNXZC" class="vomugjkpdjezjgmxstwf fafjirfvzezcugjzjnds" alt=""> to connect the SSD to my MBP via USB;</li>
    <li>Opened Disk Utility (Applications -&gt;Utilities -&gt; Disk Utility) and erased the empty SSD and formatted it (Mac OS Journaled Extended);</li>
    <li>Copied the contents of my current HD to the SSD via SuperDuper!;</li>
    <li>Replaced the old SSD with the new SSD;</li>
    <li>Set the startup disk (Settings -&gt; Startup Disk) to the installed 256GB drive. (If you install a new SSD and it takes unusually long to boot, the Startup Disk is likely not set.)</li>
</ol>

Originally I was going to add another step to this process (SuperDuper to external HD, install empty SSD, boot from external HD, copy from external HD to empty SSD) but a friend suggested that I eliminate the external HD middle-man by using a USB enclosure. Great suggestion that hadn’t crossed my mind, and it ended up saving me a load of time.

The key difference between a tool like SuperDuper! vs. Time Machine is that it allows you to create <em>fully bootable</em> backups of your hard disk, so if your machine ever goes kaput you can still boot (by holding Option during the boot up sequence and selecting the backup). At $28 for the “Smart Update” feature (only saving what’s changed between backups) it’s a great value.

BTW, if the new drive seems to freeze a lot after you upgrade (beachball for 10s or so during load), try updating your OS.  It seemed to beachball a lot until I upgraded to Mountain Lion.
