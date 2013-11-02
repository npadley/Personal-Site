---
title: Straight CSS vs. Less CSS
layout: post
comments: true
---

At my day job, I've been doing some website building. We've launched two new sites, [CD2 Learning](http://www.cd2learning.com) and [CD2 Leadership](http://www.cd2leadership.com). These two sites were my first introduction into responsive design and some higher-level web development.

I first started learning [Bootstrap](http://www.getbootstrap.com). However, I quickly needed the ability to customize the framework for another site that I'm currently building. As a result, I've been learning to work with [Less](http://www.lesscss.org).

At first, I was hesitant to get into the whole CSS preprocessor thing. My initial reaction was that using variables and mixins really weren't that big of a deal. Is it really that tough to do a find-replace for a hex value to change a color?

After using Less on my third project, I have really started to open up to the possibilities. On this project, I asked the designers to give me the four or five basic brand colors and I started using some of the color math functions. This functionality alone has won me over.

I recently had a call with the client, who asked us to tweak some of the color selections. Going back to my earlier argument about find-replace would have made this a pretty tough proposition. I would have needed to change the base brand color and the various tints that are used across the rest of the file. Using variables, I just needed to change the color in one place and recompile the CSS. I was able to do this during the meeting and show live progress.

One other thing that I've been using is a set of mixins for CSS3, which means that I only have to manage my browser specific prefixes in one place. I have gotten bit by this in the past when there was an update to the webkit or Firefox prefix, which invalidated a few gradients. Now, I only need to worry about the prefix in once place and be confident that the rest of the code will follow.

So, what would my answer be to the question of using a preprocessor? It would be a resounding "Yes!" Using a preprocessor has made things much easier and more fun. In fact, I will have a hard time starting any new web development projects without it.