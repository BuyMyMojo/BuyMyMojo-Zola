+++
title = "Optimal video encoder for sending on discord"
description = "Did some tests comparing AV1, X264 and X265 for quality, bitrate and encode time."
date = "2022-05-22"
slug = "optimal-discord-video-codec"
draft = false

[taxonomies]
tags = ["Codec", "AV1", "X264", "X265", "HEVC", "Video", "FFMPEG", "Encoding"]
+++

So I was measuring the quality and encode time of SVT-AV1 for future use with discord so for the sake of time and quality here is a table!

The target bitrate for the following video was 1077kb/s

| Format (Preset)       | SSIM   | VMAF    | Enc time in seconds | AVG bitrate | Score |
| --------------------- | ------ | ------- | ------------------- | ----------- | ----- |
| AV1 default (10)      | 0.9196 | 58.1309 | 48.147              | 1078bk/s    | 1.138 |
| AV1 (9)               | 0.9225 | 59.8840 | 61.081              | 1078kb/s    | 0.923 |
| AV1 (8)               | 0.9263 | 61.4803 | 82.480              | 1077kb/s    | 0.703 |
| AV1 (7)               | 0.9300 | 63.7214 | 119.151             | 1077kb/s    | 0.504 |
| X264 default (Medium) | 0.8446 | 19.7845 | 38.068              | 1098kb/s    | 0.494 |
| X264 (Slow)           | 0.8525 | 22.4379 | 45.265              | 1097kb/s    | 0.469 |
| X264 (Slower)         | 0.8559 | 22.6277 | 117.921             | 1097kb/s    | 0.182 |
| HEVC default (Medium) | 0.9062 | 49.4559 | 86.874              | 1103kb/s    | 0.526 |
| HEVC (slow)           | 0.9081 | 53.3164 | 192.364             | 1105kb/s    | 0.255 |
| HEVC (slower)         | 0.9189 | 57.2618 | 656.738             | 1103kb/s    | 0.08  |

<div>
<sub>The score is <quote>(((SSIM + VMAF) / 2) / AVGBitrate / EncTime) * 1000</quote> which is a measurement is more or less amount of quality for a specific file size and time.<br />
Higher is better.</sub>
</div>

The score doesn't directly reflect the quality of the video, VMAF is what you want for that, it reflects how much you would want to use it in a pinch for sending size constrained videos.

Like even though AV1(7) for the best VMAF score it took double the time as AV1(10) so you'd want to use it less.

HEVC support wont be added in discord because of licensing but I measured just because I was curious.

I made this basic "Scoring" system for choosing what settings to use when encoding videos to send on discord.

These tests where run using my AMD 5600x, there would be different speeds and time for different processors with different thread counts.

The only setting I changed for any of these encoders was the target bitrate, every other option is FFMPEG's default values.
