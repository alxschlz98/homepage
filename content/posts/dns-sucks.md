---
title: "DNS Nightmares"
subtitle: "A journey into annoyance"
description: "DNS troubles"
date: 2022-08-22T08:23:17-05:00
draft: true
featuredImage: "/images/clouds.jpg"
featuredImagePreview: "/images/clouds.jpg"

categories: [
    "personal",
]

tags: [
    "DNS",
]
---

For those of you paying attention, you might notice something new here:

***A shiny new URL!***

Now, you can go to <https://alexschulz.dev> to view this blog. I've also give it a bit of a rebrand to make it obvious it's based on me.

---

Setting up this new URL was quite the learning experience. The many, many, many guides for setting up a DNS server, and even more for setting it up via GitHub Pages.

**None of those could have prepared me for the nightmare that is DNS.**

---

### Pride

**It's Friday.**

After following the tutorial listed on GitHub, I managed to get the website up and running painlessly at https://www.alexschulz.dev. I was relieved - I managed to avoid the ever-present evil that is DNS configuration.

It wasn't until I navigated to the apex domain (wihtout the www) that I relalized what my hubris had caused. I was greeted with an SSL error, and a true understanding of the journey I'm about to undertake.

---

### Greed

**It's now Saturday.**

Surely, since I had set up the www subdomain so easily, it would be simple to get it working with just the apex domain. My first thought was to point GitHub Pages to https://alexschulz.dev, which should tell GitHub to send the certificate properly.

*NotHostedByPagesError*

I then tried to add IPv6 address to by DNS server. My assumption was that somewhere along the chain of command an IPv6 address was being thrown around, and adding GitHub Pages' IPv6 addresses would return the proper site.

But after waiting for the DNS to propogate, I was still greeted to the dreaded SSL error page. I had craved a functioning site, but was only granted errors.

---

### Gluttony

By this point, I had become obsessed with tutorials. YouTube, StackOverflow, GitHub docs, etc were all living in my browser's tab bar, each with their own simplistic little solution on how I could solve my issue.

* One told me to set up a redirect in my DNS server - infinite redirect error

* One told me to remove all of the existing A records - they weren't deletable (at least in the GUI)

* One told me to add a CNAME file to the root of my GitHub project - this was irrelevant since I'm using Pages to build my project

I searched through countless others, yet none of them gave me an answer I hadn't tried before. I was eventually led to one final YouTube video, which said to remove the CNAME for GitHub Pages and use a www A record instead. I did just that, but by this point I was exhausted from diving into the bottomless pit of tutorials.

**I gave up.**

---

### Sloth

That Sunday, I didn't touch the website. I had given up on looking at a nice, clean, and simple URL and came to the conclusion that typing out www is something that I'd have to live with. I'd be wallowing the in the filth of typing out four extra characters.

I decided to take it easy that day. I watched some TV, played some Destiny 2, made some dinner, and went to bed. Despite doing almost nothing productive, this was almost refreshing - it let me set my mind of for another full day of troubleshooting.

---

### The Final Day

**It's now Monday.**

I'm four cardinal sins and some coffee down, and I'm ready to tackle this DNS website once and for all.

I navigate to <https://alexschulz.dev>, and I'm greeted to a shiny and clean static website, hosted by me.

Well, that was easy. Turns out waiting really helps with DNS issues.
