---
title: Learning HUGO
description: HUGO is an interesting tool.
tags: [learning, open-source, hugo]
date: 2021-12-09T17:16:00+11:00
slug: learning-hugo
image: /img/vendor/hugo.svg
author: "Owen Quinlan"
draft: false
---

![HUGO logo](/img/vendor/hugo.svg)

## #Learning HUGO was interesting

So right off the bat I decided to make something [less then normal](https://shell.buymymojo.net/) to learn some basics and it was pretty fun, I then moved to actually learning how to create this main website.

### Dates are weird

A major issue I had while making this very page was adding a date, I tried to give it the date `2021-12-09T17:16:00` which was the exact time I started to write the page after consulting [Heap](https://gitlab.com/HeapUnderflow) about the date issue, They informed me I cannot make dates that are in the future.

I'm Australian so all my dates are in the futue, I have the UTC offset of +10 but even setting the offset to that `2021-12-09T17:16:00+10:00` it would still have an issue and not appear on my page, AS IT TURNS OUT I need to tell it I'm half way between east australia and New Zealand and set my UTC offset to +11 `2021-12-09T17:16:00+11:00`

After that it was smooth sailing, here is the header info from the `.md` file making up this page:

```markdown
---
title: Learning HUGO
description: HUGO is an interesting tool.
tags:
- learning
- open-source
- code
date: 2021-12-09T17:16:00+11:00
slug: learning-hugo
image: /img/vendor/hugo.svg
---
```

Pretty simple right?

Adding an image to the preview render has been a pain in my butt :triumph:

![Preview of Facebook share](/img/screencaps/share-preview-20211209-1912.png)
![Preview of Twitter share](/img/screencaps/share-preview-20211209-1913.png)

The theme in use on this website provides the ability to have Open Graph tags for each page, a slight issue is that it only allows you to use global image instead of an image for each specific post which is kinda sad.

In order to have the image above (Art by [Weaves](https://twitter.com/Weaveasy)) I had to set a global image inside of my HUGO config file:

```toml
[Params]
    og_image = "https://wip.buymymojo.net/img/og-image.png"
```

I'm going to put a request into the theme's repo for support for a per post image but ofc if it doesnt add it that's fine. It's an open source theme for an open source tool, if I eventually learn HUGO more intametly I will make my own fork and link it here!

#### One final hiccup

In this theme if there is a folder `/pages` and a folder `/posts` it will only display the posts inside of `/pages` on the front page, if you remove it then it shows the files in `/pages` so I've moved to only using the pages folder

Go check out the source for this website [here](https://gitlab.com/BuyMyMojo/buymymojo-hugo) and the theme [here](https://github.com/athul/archie)
