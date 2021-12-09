---
title: Learning HUGO
description: HUGO is an interesting tool.
tags: [learning, open-source, hugo]
date: 2021-12-09T17:16:00+11:00
slug: learning-hugo
image: /img/vendor/hugo.svg
draft: true
---

![HUGO logo](https://buymymojo.gitlab.io/buymymojo-hugo/img/vendor/hugo.svg)

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

Go check out the source for this website [here](https://gitlab.com/BuyMyMojo/buymymojo-hugo) and the theme [here](https://github.com/athul/archie)
