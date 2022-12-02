+++
title = "Learning HUGO"
description = "HUGO is an interesting tool."
date = "2021-12-09"
slug = "learning-hugo"
draft = false

[taxonomies]
tags = ["learning", "open-source", "hugo"]
+++

## Update! 2022-11-29

I have now moved over to [Zola](https://www.getzola.org/), A rust based static site generator. It is pretty simalar to hugo but I will eventually make a post like this about Zola and it's differences.

<h1 class="post-title"></h1>
<sub>
Fun thing: to get this line seperating I had to write it as:

```html
<h1 class="post-title"></h1></code>
```

</sub>

<!-- nice my first shortcode was pretty easy to bring over to Zola -->
{{ triimg(name="hugo_small", alt="HUGO logo") }}

## Learning HUGO was interesting

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

{{ triscreencap(name="share-preview-20211209-1912", alt="Preview of Facebook share")}}

{{ triscreencap(name="share-preview-20211209-1913", alt="Preview of Twitter share")}}

The theme in use on this website provides the ability to have Open Graph tags for each page, a slight issue is that it only allows you to use global image instead of an image for each specific post which is kinda sad.

In order to have the image above (Art by [Weaves](https://twitter.com/Weaveasy)) I had to set a global image inside of my HUGO config file:

```toml
[Params]
    og_image = "https://wip.buymymojo.net/img/og-image.png"
```

I'm going to put a request into the theme's repo for support for a per post image but ofc if it doesnt add it that's fine. It's an open source theme for an open source tool, if I eventually learn HUGO more intametly I will make my own fork and link it here!

#### One final hiccup

In this theme if there is a folder `/pages` and a folder `/posts` it will only display the posts inside of `/pages` on the front page, if you remove it then it shows the files in `/pages` so I've moved to only using the pages folder

So the current strcture is:

```txt
buymymojo-hugo/
├── archtypes/
│   └── default.md
├── content/
│   └── posts/
│       ├── 2021-12-09-learning-hugo.md
│       └── about.md
├── static/
│   ├── img/
│   │   ├── screencaps/
│   │   │   ├── share-preview-20211209-1912.png
│   │   │   └── share-preview-20211209-191348.png
│   │   ├── vendor/
│   │   │   ├── hugo.png
│   │   │   └── hugo.svg
│   │   └── og-image.png
│   ├── android-chrome-192x192.png
│   ├── android-chrome-512x512.png
│   ├── apple-touch-icon.png
│   ├── favicon-16x16.png
│   ├── favicon-32x32.png
│   ├── favicon.ico
│   └── site.webmanifest
├── themes/
│   └── archie
├── .gitignore
├── .gitlab-ci.yml
├── config_pages.toml
├── config.toml
├── LICENSE
└── README.md
```

Go check out the [source for this website](https://gitlab.com/BuyMyMojo/buymymojo-hugo) and the [theme used here](https://github.com/athul/archie)

<sub>
<p>Credit to <a href="https://anaulin.org/blog/hugo-raw-html-shortcode/">Ana Ulin</a> for their raw HTML shortcode example I am now using</p>
</sub>
