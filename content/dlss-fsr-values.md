+++
title = "DLSS-FSR experiments"
description = "A collection of measurements and tests using DLSS and FSR."
date = "2022-05-05"
updated = "2022-11-29"
slug = "dlss-fsr-exp"
in_search_index = true
weight = 1
draft = true

[taxonomies]
tags = ["DLSS", "FSR"]
+++

## DLSS/FSR Resolution table

<sub>I run 1440p on my monitors so that will be my main testing resolution</sub>

{{ figure(src="/img/webp/FSR_DLSS-Res.webp",
          style="width: 100%;",
          position="center"
          caption_position="center",
          caption="A table of some known resolutions",
          caption_style="font-weight: bold; font-style: italic;") }}

<!-- The table bellow is the origional code for the table but it broken when converting to zola. -->
<!-- an archive of the origional post with the table can be found at <https://web.archive.org/web/20221129123333/https://wip.buymymojo.net/posts/2022/05/05/dlss-fsr-experiments/> -->
<!-- <table>
  <tbody>
    <tr>
      <th class="heading" colspan="15">AMD FSR vs NVIDIA DLSS Resolutions</th>
    </tr>
    <tr>
      <th>BuyMyMojo.net</th>
      <th>
        Native<br />
        Resolution
      </th>
      <th>
        Scale<br />
        Factor
      </th>
      <th></th>
      <th colspan="2">8192×4320 (8K)</th>
      <th></th>
      <th colspan="2">3840×2160 (4K)</th>
      <th></th>
      <th colspan="2">2560×1440 (Ours)</th>
      <th></th>
      <th colspan="2">1920×1080</th>
    </tr>
    <tr>
      <th colspan="15">NVIDIA DLSS</th>
    </tr>
    <tr>
      <td><strong>Quality</strong></td>
      <td><strong>66.6%</strong></td>
      <td><strong>1.50x</strong></td>
      <th rowspan="4"></th>
      <td>5461</td>
      <td>2880</td>
      <th rowspan="4"></th>
      <td>2560</td>
      <td>1440</td>
      <th rowspan="4"></th>
      <td>1707</td>
      <td>960</td>
      <th rowspan="4"></th>
      <td>1280</td>
      <td>720</td>
    </tr>
    <tr>
      <td><strong>Balanced</strong></td>
      <td><strong>58.0%</strong></td>
      <td><strong>1.72x</strong></td>
      <td>4752</td>
      <td>2506</td>
      <td>2227</td>
      <td>1253</td>
      <td>1485</td>
      <td>835</td>
      <td>1114</td>
      <td>626</td>
    </tr>
    <tr>
      <td><strong>Performance</strong></td>
      <td><strong>50.0%</strong></td>
      <td><strong>2.00x</strong></td>
      <td>4096</td>
      <td>2160</td>
      <td>1920</td>
      <td>1080</td>
      <td>1280</td>
      <td>720</td>
      <td>960</td>
      <td>540</td>
    </tr>
    <tr>
      <td><strong>Ultra Performance</strong></td>
      <td><strong>33.3%</strong></td>
      <td><strong>3.00x</strong></td>
      <td>2731</td>
      <td>1440</td>
      <td>1280</td>
      <td>720</td>
      <td>853</td>
      <td>480</td>
      <td>640</td>
      <td>360</td>
    </tr>
    <tr>
      <th colspan="15">AMD FSR</th>
    </tr>
    <tr>
      <td><strong>Ultra Quality&nbsp;</strong></td>
      <td><strong>77.0%</strong></td>
      <td><strong>1.30x</strong></td>
      <th rowspan="4"></th>
      <td>6302</td>
      <td>3323</td>
      <th rowspan="4"></th>
      <td>2954</td>
      <td>1662</td>
      <th rowspan="4"></th>
      <td>1970</td>
      <td>1108</td>
      <th rowspan="4"></th>
      <td>1970</td>
      <td>831</td>
    </tr>
    <tr>
      <td><strong>Quality</strong></td>
      <td><strong>66.6%</strong></td>
      <td><strong>1.50x</strong></td>
      <td>5461</td>
      <td>2880</td>
      <td>2560</td>
      <td>1440</td>
      <td>1706</td>
      <td>960</td>
      <td>1706</td>
      <td>720</td>
    </tr>
    <tr>
      <td><strong>Balanced</strong></td>
      <td><strong>58.8%</strong></td>
      <td><strong>1.70x</strong></td>
      <td>4819</td>
      <td>1270</td>
      <td>2259</td>
      <td>1270</td>
      <td>1506</td>
      <td>847</td>
      <td>1129</td>
      <td>635</td>
    </tr>
    <tr>
      <td><strong>Performance</strong></td>
      <td><strong>50.0%</strong></td>
      <td><strong>2.00x</strong></td>
      <td>4096</td>
      <td>2160</td>
      <td>1920</td>
      <td>1080</td>
      <td>1280</td>
      <td>720</td>
      <td>960</td>
      <td>540</td>
    </tr>
  </tbody>
</table> -->
