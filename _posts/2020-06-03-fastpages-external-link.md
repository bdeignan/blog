---
layout: post
title: "Linking to another website from fastpages"
description: Quick example of how to link to an external page from a fastpages blog.
categories: [fastpages, meta]
image: images/meta.png
---

My inaugural post on here is a bit meta and probably unlike most things that I’ll write. 

First, this blog is built with [fastpages](https://github.com/fastai/fastpages). If you're like me and work with Jupyter notebooks all the time, then fastpages makes it a breeze to turn them into blog posts. There's a whole lot more you can do with fastpages mentioned in the Twitter thread below. I love everything fast.ai does, and this tool is no exception.

{% twitter https://twitter.com/jeremyphoward/status/1232059428238581760?s=20 %}

Outside of this blog, I have a personal website and I wanted them to blend together as seamlessly as (a data scientist like me can make) possible.

Luckily, a [fastpages GitHub issue](https://github.com/fastai/fastpages/issues/169) addresses this very thing and one of the primary fastpages contributors already posted some helpful links there. 

But I also like to see concrete examples. So, if you’re the same, then hopefully this helps.

It’s a pretty simple fix. I wanted to link to an external “about me” page where I keep an updated resume. To do this, I removed the “about” markdown file from the `/_posts` directory and replaced it with an html file. This is what the html file looks like:

```html
--- 
title: About
search_exclude: true 
--- 
<meta charset="utf-8">
<title>Redirecting to https://bdeignan.github.io/about</title>
<meta http-equiv="refresh" content="0; URL=https://bdeignan.github.io/about">
<link rel="canonical" href="https://bdeignan.github.io/about">
```

It pretty much follows [one of the links](https://dev.to/steveblue/setup-a-redirect-on-github-pages-1ok7) provided in the issue's comment.

The main thing you’ll want to change is the URL linked to. Substitute your page for `https://bdeignan.github.io/about` above.

And, voila. I pushed the changes to my blog's repo and now “About” sends you to my personal site. 

This lets me keep my blog separate from my personal site – in case I want to change things in the future to one of them. I find the fastpages blog setup so convenient for data science posts but I may want to change my personal site in the future if I get bored enough to learn some web development skills. This separation should help make those changes easier to maintain.
