+++
title = "Extreme NVENC OBS profile"
description = "OBS NVENC video encoding is actually pretty fun!"
date = "2022-01-04"
slug = "extreme-obs-profile"
draft = true

[taxonomies]
tags = ["learning", "obs", "ffmpeg", "video", "encoding"]
+++

{{< tri-screencap name="Profile_Screencap" alt="List of all temps" >}}

## What is the point?

The reason for this profile is to acieve the highest quality possible using NVENC on the 20xx/30xx Nvidia GPUs

## Settings:

### Video Bitrate:

I use `45,000 Kbps` average and `80,000 Kbps` max for 1140p60 recording but I will get some more percise numbers for multiple resolutions soon!

### Keyframe interval

You can leave this at double frame rate but for the sake of increasing overal quality slighty I did `115` instead of `120`.

This shouldn't actually change too much but this is meant to be a slight overkill profile.

### Video Encoder:

Here I am using `h264_nvenc` since it is a tried and known codec but these settings should also work for `hevc_nvenc` too if you want.

I'll try to get some more specific quality numbers for this too!

### Video Encoder Settings

Now here is some special sauce! My settings are a modified version of [Xaymar's OBS streaming settings](https://www.xaymar.com/guides/obs/high-quality-streaming-nvenc/) 

<sub>This post was made after he started to move his website to the new style, as of writing his [Recording settings](https://www.xaymar.com/guides/obs/high-quality-recording/) aren't avaliable<sub>

#### `2pass`

The use of `2pass` is based of Xaymar's recomendations for Turing & Ampere cards but this will be further explored during my quality testing.

I know it is more useful in a Streaming situation since it helps keep the bitrate more consistent but according to the [FFMPEG website](https://trac.ffmpeg.org/wiki/Encode/H.264#twopass) it can lower the quality some what?

#### `multipass`

This option is NVENC specific and is similar to `2pass` but helps the NVENC encoder decide how to distribute the bitrate across the from and how many bits it will require as well and let's the encoder decide what QP level to use for parts of the frame

This has two modes; `first pass in quarter resolution and second pass in full resolution` and `both passes in full resolution`

According to the [Nvidia docs](https://docs.nvidia.com/video-technologies/video-codec-sdk/nvenc-video-encoder-api-prog-guide/#multi-pass-frame-phencoding) full resolution mode generates better stats for the second pass but the quater resolution mode gets larger motion vectors which can posibly help with objects that move across the screen faster(?). As with all things in this post I will look into it more when i do proper quality testing.

#### `spatial-aq` & `temporal-aq`

The `spatial-aq` option helps the NVENC encoder use it's bitrate more efficiently in places that need details instead of areas that dont actually have any detail

The [Nvidia docs](https://docs.nvidia.com/video-technologies/video-codec-sdk/nvenc-video-encoder-api-prog-guide/#spatial-aq) say `the required bit redistribution results in PSNR drop in most of the cases.` which makes sense but is good to keep in mind when looking for quality mterics, when testing later I will use SSIM and VMAF scores to gague quality!

The `temporal-aq` options checks through the frames within the `rc-lookahead` area to see what ones of those frames require bitrate more compared to the others

#### `rc-lookahead`

`rc-lookahead` improves the overal quality of the video by allowing the encoder to look over the buffered frames to estimate the complexity of the frames to more efficiently distrabute the bitrate and to also allocate B and P frames

#### `profile`

According to [RGB Spectrum](https://www.rgb.com/h264-profiles#:~:text=High%20Profile-,H.,ratio%20of%20about%202000%3A1.) the High profile is the most efficient profile, I'm pretty sure this just decides default settings for the actual h264 format(?)

### `preset`

This changes the preset settings for a bunch of the settings the encoder uses, `p7` is the "slowest" and highest quality mode in the latest versions of FFMPEG and OBS.

Even though it is called the "slowest" it can still get over 100FPS on my 1440p footage when using FFMPEG directly



