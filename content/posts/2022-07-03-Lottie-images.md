---
title: Lottie images
description: Lottie animated images are an interesting thing
tags: [learning, obs, ffmpeg, video, encoding]
date: 2022-03-06T13:05:33+11:00
slug: lottie-images
author: "Owen Quinlan"
draft: true
---

{{< rawhtml >}}
<script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
<script src="https://unpkg.com/@lottiefiles/lottie-interactivity@latest/dist/lottie-interactivity.min.js"></script>
{{< /rawhtml >}}


## This is a Lottie image:

{{< rawhtml >}}
<lottie-player src="https://assets5.lottiefiles.com/packages/lf20_mbe3iiji.json"  background="transparent"  speed="1"  style="width: 100%;"  loop controls autoplay></lottie-player>
{{< /rawhtml >}}

## This is the same image as a gif:

{{< rawhtml >}}
<img src="https://files.buymymojo.net/jb27k3aqhzpv.gif" style="width: 100%;" />
{{< /rawhtml >}}

## What is the difference?

The 640x640 GIF image is `2.53MB` while Lottie image is ajust a `124KB` .json file which when served with gzip it becomes only `13KB` and even better when served with zstd(Speed 9) becomes only `9KB`. That is a massive saving for a detailed and smooth animation.

Of course you can't really converting a normal gif to a Lottie because it is on the most basic level an [animated svg](https://lottiefiles.com/svg-to-lottie) file it is still a very valuable resource for having animated vectors on a website.

Another thing you can do with this file format is easilty animate it based on the scroll of a website, have the animation only play once, have it play at different speeds

{{< rawhtml >}}
<lottie-player id="firstLottie" src="https://assets5.lottiefiles.com/packages/lf20_mbe3iiji.json" style="width:100%;">"></lottie-player>

<script>
LottieInteractivity.create({
  mode: 'scroll',
  player: '#firstLottie',
  actions: [
      {
        visibility: [0,1],
        type: 'seek',
        frames: [0, 120],
      },
    ],
});
</script>
{{< /rawhtml >}}

## Easy customisation

The official website has a very simple and easy tool to modify the Lottie's colours to fit your website better, here is one I changed to be sligthly closer to this website's colours:

{{< rawhtml >}}
<lottie-player src="https://assets10.lottiefiles.com/packages/lf20_wo2kiemb.json"  background="transparent"  speed="1"  style="width: 100%;"  loop controls></lottie-player>
{{< /rawhtml >}}
