---
title: Concepts
subtitle: null
copytitle: "Responsive or not, there’s no reason why we shouldn’t all be designing and building sites on flexible foundations."
abstract: null
published: true
categories: 
  - articles
  - chapter1
layout: article
tags: 
  - open
  - hardware
  - design
splash: null
category: blog
---

![2014-08-06 16.36.22.png](/_posts/articles/2014-08-06 16.36.22.png)

This concept is nothing new, having been prophetically outlined in Jon Allsopp’s 2000 article, [A Dao of Web Design](http://www.alistapart.com/articles/dao/). Sadly, I’m able to count myself among the many who, until recently, have failed to see the benefits of embracing the inherent flexibility of the web. [Andy Hume](http://blog.andyhume.net/responsive-by-default/) states it well:

> The web is responsive on its own—by default. It’s us that’s been breaking it all these years by placing content in fixed-width containers.

And here I thought I was doing the web a huge favor with my fixed pixel-based layouts. That isn’t to say that sites I built with Paravel well before RWD aren’t good, but their pixel-based layouts make them far less portable. Good design could have been made better had we grasped the benefits of the flexible foundation years earlier.

## Flexibility Applied

Let’s take the difference between [button #1 and button #2 as an example](http://codepen.io/TrentWalton/pen/sCgBq). Visually, they’re identical across media queried changes, but because button #2 was built on a flexible foundation (using relative units[^1] and percentages), it scales proportionally with media queried font-size changes or when users increase their browser default font size. Button #1 requires extra code to keep everything to scale because of the pixel values set for padding. In many ways, every time we use a pixel value in CSS we’re rasterizing what was a fully-scalable web.[^2]

Extra code like this adds up. With Paravel’s first few responsive projects we were so fixated with the 3 key ingredients (flexible grids, flexible images, and media queries) that we still used pixel values inside of our flexible grid. Thus, we needed to rewrite the vast majority of our CSS from one media query to the next in order to keep things proportional.

![bild](http://pcdn.paravel.netdna-cdn.com/wp-content/uploads/2013/04/fig1.jpg)

See this example #1 of a tiny site. By definition, it is responsive. There are flexible images, flexible grids, and media queries. But notice how much CSS is packed into each media query. Now, see example #2. It’s the exact same site, but because it’s built on a flexible foundation the entire thing scales from one media query to the next with a single font size change. Everything subsequently utilizes a relative unit so it scales proportionally no matter what.

This paid off a few weeks ago, when a client wanted to make significant changes to the layout for his site. Type, imagery, buttons, etc. needed to be smaller and overall width & spacing (margins / padding) needed to be reduced. Thankfully, this was as simple as adjusting the body font-size at wide views. Years ago, however, this could have set the project weeks beyond scoped timeline and budget.

If I could go back in time 3 years I’d tell myself that the red jacket is going to make me look like an asshole. Then I’d slap myself and point out that flexible grids and flexible images are great, but ultimately I should be focused on making things truly scalable by thinking twice before I used pixel values in my CSS. Perhaps that’s what RWD really should be defined as in the end—sites built on a fully-flexible foundation enhanced by media queries.

The sites we’ve built to display on a desktop, smartphone, or a tablet today could be on a TV Screen, coffee table display, or mega space yacht projection system tomorrow. Do yourself a favor and heed the advice of the Dao:

> The web’s greatest strength, I believe, is often seen as a limitation, as a defect. It is the nature of the web to be flexible, and it should be our role as designers and developers to embrace this flexibility and produce pages which, by being flexible, are accessible to all.



[^1]: Style sheets that use [relative units](http://www.w3.org/TR/css3-values/#relative-lengths) can more easily scale from one output environment to another. Most of the time I use em and rem.
[^2]: I’m sure there are occasional exceptions.

