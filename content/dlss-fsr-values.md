+++
title = "DLSS-FSR experiments"
description = "A collection of measurements and tests using DLSS and FSR."
# date = "2022-05-05"
date = "2023-05-01"
updated = "2023-05-01"
slug = "dlss-fsr-exp"
in_search_index = true
weight = 1
draft = false

[taxonomies]
tags = ["DLSS", "FSR", "FSR 1.0", "FSR 2.0", "XeSS", "NVIDIA", "AMD", "Intel"]
+++

## Resolution table

<!-- an archive of the old post with the table can be found at <https://web.archive.org/web/20221129123333/https://wip.buymymojo.net/posts/2022/05/05/dlss-fsr-experiments/> -->
<!-- table has been updated to XeSS as I am getting an Intel A770 and decided to look into it! Also added FSR 2.0 because I forgot to do that -->
<table cellpadding="0" cellspacing="0">
 <thead>
 </thead>
 <tbody>
  <tr style="height: 20px">
   <td class="heading" colspan="11"><center>NVIDIA DLSS, AMD FSR 1.0, AMD FSR 2.0 and Intel XeSS Resolutions</center></td>
  </tr>
  <tr style="height: 20px">
   <td><a href="http://buymymojo.net/" target="_blank">BuyMyMojo.net</a></td>
   <td>Native Resolution</td>
   <td>Scale Factor</td>
   <td colspan="2">8192&times;4320 (8K)</td>
   <td colspan="2">3840&times;2160 (4K)</td>
   <td colspan="2">2560&times;1440 (1440p)</td>
   <td colspan="2">1920&times;1080 (1080p)</td>
  </tr>
  <tr style="height: 20px">
   <td colspan="11"><center>NVIDIA DLSS</center></td>
  </tr>
  <tr style="height: 20px">
   <td>Quality</td>
   <td>66.60%</td>
   <td>1.50x</td>
   <td>5461</td>
   <td>2880</td>
   <td>2560</td>
   <td>1440</td>
   <td>1707</td>
   <td>960</td>
   <td>1280</td>
   <td>720</td>
  </tr>
  <tr style="height: 20px">
   <td>Balanced</td>
   <td>58.00%</td>
   <td>1.72x</td>
   <td>4752</td>
   <td>2506</td>
   <td>2227</td>
   <td>1253</td>
   <td>1485</td>
   <td>835</td>
   <td>1114</td>
   <td>626</td>
  </tr>
  <tr style="height: 20px">
   <td>Performance</td>
   <td>50.00%</td>
   <td>2.00x</td>
   <td>4096</td>
   <td>2160</td>
   <td>1920</td>
   <td>1080</td>
   <td>1280</td>
   <td>720</td>
   <td>960</td>
   <td>540</td>
  </tr>
  <tr style="height: 20px">
   <td>Ultra Performance</td>
   <td>33.30%</td>
   <td>3.00x</td>
   <td>2731</td>
   <td>1440</td>
   <td>1280</td>
   <td>720</td>
   <td>854</td>
   <td>480</td>
   <td>640</td>
   <td>360</td>
  </tr>
  <tr style="height: 20px">
   <td colspan="11"><center>AMD FSR 1.0</center></td>
  </tr>
  <tr style="height: 20px">
   <td>Ultra Quality</td>
   <td>77.00%</td>
   <td>1.30x</td>
   <td>6302</td>
   <td>3323</td>
   <td>2954</td>
   <td>1662</td>
   <td>1970</td>
   <td>1108</td>
   <td>1477</td>
   <td>831</td>
  </tr>
  <tr style="height: 20px">
   <td>Quality</td>
   <td>66.60%</td>
   <td>1.50x</td>
   <td>5461</td>
   <td>2880</td>
   <td>2560</td>
   <td>1440</td>
   <td>1706</td>
   <td>960</td>
   <td>1280</td>
   <td>720</td>
  </tr>
  <tr style="height: 20px">
   <td>Balanced</td>
   <td>58.80%</td>
   <td>1.70x</td>
   <td>4819</td>
   <td>1270</td>
   <td>2259</td>
   <td>1270</td>
   <td>1506</td>
   <td>847</td>
   <td>1129</td>
   <td>635</td>
  </tr>
  <tr style="height: 20px">
   <td>Performance</td>
   <td>50.00%</td>
   <td>2.00x</td>
   <td>4096</td>
   <td>2160</td>
   <td>1920</td>
   <td>1080</td>
   <td>1280</td>
   <td>720</td>
   <td>960</td>
   <td>540</td>
  </tr>
  <tr style="height: 20px">
   <td colspan="11"><center>AMD FSR 2.0</center></td>
  </tr>
  <tr style="height: 20px">
   <td>Quality</td>
   <td>66.60%</td>
   <td>1.50x</td>
   <td>5461</td>
   <td>2880</td>
   <td>2560</td>
   <td>1440</td>
   <td>1706</td>
   <td>960</td>
   <td>1280</td>
   <td>720</td>
  </tr>
  <tr style="height: 20px">
   <td>Balanced</td>
   <td>58.80%</td>
   <td>1.70x</td>
   <td>4819</td>
   <td>1270</td>
   <td>2227</td>
   <td>1253</td>
   <td>1506</td>
   <td>847</td>
   <td>1129</td>
   <td>635</td>
  </tr>
  <tr style="height: 20px">
   <td>Performance</td>
   <td>50.00%</td>
   <td>2.00x</td>
   <td>4096</td>
   <td>2160</td>
   <td>1920</td>
   <td>1080</td>
   <td>1280</td>
   <td>720</td>
   <td>960</td>
   <td>540</td>
  </tr>
  <tr style="height: 20px">
   <td>Ultra Performance</td>
   <td>33.3</td>
   <td>3.0x</td>
   <td>2731</td>
   <td>1440</td>
   <td>1280</td>
   <td>720</td>
   <td>854</td>
   <td>480</td>
   <td>640</td>
   <td>360</td>
  </tr>
  <tr style="height: 20px">
   <td colspan="11"><center>Intel XeSS</center></td>
  </tr>
  <tr style="height: 20px">
   <td>Ultra Quality</td>
   <td>76.69%</td>
   <td>1.304x?</td>
   <td>6282</td>
   <td>3312</td>
   <td>2944</td>
   <td>1656</td>
   <td>1962</td>
   <td>1104</td>
   <td>1472</td>
   <td>828</td>
  </tr>
  <tr style="height: 20px">
   <td>Quality</td>
   <td>66.60%</td>
   <td>1.50x</td>
   <td>5461</td>
   <td>2880</td>
   <td>2560</td>
   <td>1440</td>
   <td>1706</td>
   <td>960</td>
   <td>1280</td>
   <td>720</td>
  </tr>
  <tr style="height: 20px">
   <td>Balanced</td>
   <td>58.34%</td>
   <td>1.714x</td>
   <td>4779</td>
   <td>2520</td>
   <td>2240</td>
   <td>1260</td>
   <td>1493</td>
   <td>840</td>
   <td>1120</td>
   <td>630</td>
  </tr>
  <tr style="height: 20px">
   <td>Performance</td>
   <td>50.00%</td>
   <td>2.00x</td>
   <td>2731</td>
   <td>1440</td>
   <td>1920</td>
   <td>1080</td>
   <td>1280</td>
   <td>720</td>
   <td>960</td>
   <td>540</td>
  </tr>
 </tbody>
</table>

<a href="https://web.archive.org/web/20221129123333/https://wip.buymymojo.net/posts/2022/05/05/dlss-fsr-experiments/">
{{ figure(src="/img/webp/FSR_DLSS-Res.webp",
          style="width: 75%;",
          position="center"
          caption_position="center",
          caption="Old version of the table",
          caption_style="font-weight: bold; font-style: italic;") }}
</a>
<sub>click image above to view an archive</sub>
