+++
title = "proton and linux gaming things [V1.0]"
description = "This will be a post I update over time with gaming stuff that I find helpful on linux"
date = "2021-12-15"
slug = "proton-and-linux"
draft = false

[taxonomies]
tags = ["linux", "gaming", "proton", "wine"]
+++

<!-- Preset for the link: https://tree.nathanfriend.io/?s=(%27VCs!(%27fancy!Kue~fullPath!false~KailEgSlash!Kue~roHDH!false)~G(%27G%27LEksR3DLSS%20C%20LO*dlss-C-lOXSteam*steamXL7*l7083L7%206*l7-6WFPS%20Q*fps-QWPrHC4prHC-2XNvidia4nvidiaBAMD4amdBIntel4EtelBUJ4uJ-2s5%27)~9siC!%271%27)*%5D%7B((%3C%20ref%20TphHC-and-lO.md%2305R82VmisatiC38%5B4%202*5T%20%3E))%7D6KoubleshoHEg7uKis8%20%209verB-2sXConEinGsource!HotJni9salKtrOEuxQo9layR%5CnT%5C%27VoptiW0%5BX03%01XWVTRQOKJHGECB987654320* -->

<!-- Replace every indent with: &nbsp;&nbsp;&nbsp;&nbsp; -->

Links/  
├── [DLSS on Linux]({{< ref "photon-and-linux.md#dlss-on-linux" >}})/  
│&nbsp;&nbsp;&nbsp;&nbsp;├── [Steam]({{< ref "photon-and-linux.md#steam" >}})  
│&nbsp;&nbsp;&nbsp;&nbsp;└── [Lutris]({{< ref "photon-and-linux.md#lutris" >}})/  
│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── [Lutris troubleshooting]({{< ref "photon-and-linux.md#lutris-troubleshooting" >}})  
├── [FPS overlay]({{< ref "photon-and-linux.md#fps-overlay" >}})  
└── [Proton optimisation]({{< ref "photon-and-linux.md#proton-optimisation" >}})/  
&nbsp;&nbsp;&nbsp;&nbsp;├── [Nvidia optimisation]({{< ref "photon-and-linux.md#nvidia-optimisations" >}})  
&nbsp;&nbsp;&nbsp;&nbsp;├── [AMD optimisation]({{< ref "photon-and-linux.md#amd-optimisations" >}})  
&nbsp;&nbsp;&nbsp;&nbsp;├── [Intel optimisation]({{< ref "photon-and-linux.md#intel-optimisations" >}})  
&nbsp;&nbsp;&nbsp;&nbsp;└── [Universal optimisation]({{< ref "photon-and-linux.md#universal-optimisations" >}})  

<sub>
The permalink for this page is <a href="https://buymymojo.net/linux/proton-and-linux">https://buymymojo.net/linux/proton-and-linux</a>, keep that in your bookmarks if you want to check back on this post later!
</sub>

## DLSS on linux

So first of all I do use nvidia GPUs for a few reasons, DLSS and NVENC being a couple so here is a quick guide on how to use DLSS on linux:

### Steam

To run steam Proton games with dlss you just need to add a couple of launch options:

For DX12 games:

```
PROTON_ENABLE_NVAPI=1 %command%
```

For DX11 games (Also use with DX12 if you're having issues):

```
PROTON_HIDE_NVIDIA_GPU=0 PROTON_ENABLE_NVAPI=1 %command%
```

### Lutris

To run Lutris games with dlss it is a very simple toggle!

Right click the game > `Config` > `Runner options` tab > `Enable DXVK-NVAPI / DLSS`

It might be enabled by default already

<a href="/img/screencaps/enable-dlss-lutris/EnableDLSS.gif">
<picture loading="lazy">
    <source type="image/webp" srcset="/img/screencaps/enable-dlss-lutris/EnableDLSS.webp" style="width: 100%;" loading="lazy" decoding="async">
    <img src="/img/screencaps/enable-dlss-lutris/EnableDLSS.gif" alt="HUGO logo" style="width: 100%;" loading="lazy" decoding="async">
</picture>
</a>

#### Lutris troubleshooting

I had an issue where `Cyberpunk 2077` wouldnt let me enable dlss after this feature was added, if you have an issue where you ran the game without DLSS enabled and now it wont let you enable it at all then this might fix it for you;

1. go to the game's files
    - in my case it was in `~/Games/cyberpunk2077/drive_c/GOG Games/Cyberpunk 2077/`
2. delte the `d3d11.log` and `dxgi.log` files.
    - For me the files where named `Cyberpunk2077_d3d11.log` and `Cyberpunk2077_dxgi.log` so the file might have the games name in it for you too.
3. Enable DLSS and run again

## FPS overlay

Having a good FPS overlay is always a useful tool.

The best overlay I've found is [Mangohud](https://github.com/flightlessmango/MangoHud).

<img src="https://raw.githubusercontent.com/flightlessmango/MangoHud/master/assets/overlay_example.gif" alt="Overlay example" loading="lazy" decoding="async">
<br>
<sub> Credit: The Mangohud github page </sub>

The easiest way to configure Mangohud how you'd like it is to use [Goverlay](https://github.com/benjamimgois/goverlay)

<img src="https://i.ibb.co/QktWGxz/goverlay062-1c.jpg" alt="Goverlay example" loading="lazy" decoding="async">
<br>
<sub> Credit: The Goverlay github page </sub>

## Proton optimisation

While a lot of games run with equal to or greater then windows performance now there are always some optimisations to make the experince more smooth. Hopefully in the future devs will provide presets for these on linux with the launch of the steam deck

### Nvidia optimisations

I did say that I run an Nvidia card so this will be my starting point.

- `__GL_THREADED_OPTIMIZATION=1`
  - For OpenGL games this can give a performance boost.
- `__GL_SHADER_DISK_CACHE=1`
  - This will cache shaders as they are compiled so the gpu doesnt need to compile them again. Not all games need this but it can reduce stuttering more and more as you play.
- `__GL_SHADER_DISK_CACHE_PATH=/path/to/location`
  - This sets the location for the shader cache. I typically just put a `/cache` folder inside my game's folder.

### AMD optimisations

I dont have an AMD card to test any of these on so refer to [the ProtonDB page](https://www.protondb.com/help/improving-performance) for more info

- Install Mesa drivers for AMD cards
  - Refer to the DB page
  - Using a mesa drive past version 19.3 will let steam use their newer [ACO](https://steamcommunity.com/games/221410/announcements/detail/1602634609636894200) shader compiler
- `mesa_glthread=true`
  - Like `__GL_THREADED_OPTIMIZATION=1` but for AMD

### Intel Optimisations

There arent any dedicated Intel GPUs in the wild for gaming yet, silly.

I will update this section when we get some actual information about them!

### Universal optimisations

These are some optimisations that work on all GPU providers

- [Feral Gamemode](https://github.com/FeralInteractive/gamemode)
  - This is a tool made by Feral Interactive, They have ported games like `Total War: ROME REMASTERED`, `Shadow of the Tomb Raider` and `Life is Strange: Before the Storm` to linux!
  - The tweaks in this tool are typically already active in their own games but adding this to other Proton games can provide further performance imporovements in CPU limited situations
  - It can be installed via your package manager of built using their git repo
  - Add it to your steam game launch options like so: `gamemoderun %command%`
  - There is a toggle for this inside of Lutris too!
- Custom Proton/Wine builds
  - [GloriousEggroll Proton](https://github.com/GloriousEggroll/proton-ge-custom) this version typically provides extra fixes onto the current experimental version of Proton
  - [GloriousEggroll Wine](https://github.com/GloriousEggroll/wine-ge-custom) these are basically the game builds but for use with Lutris or just to run normal Windows software

<br>
<sub>
Credits: <br>
GamingOnLinux; I found the <a href="https://www.gamingonlinux.com/2021/10/proton-experimental-expands-nvidia-dlss-support-on-linux-to-directx-11-titles/">DX11</a> and <a href="https://www.gamingonlinux.com/2021/10/steam-play-proton-63-7-is-out-now-proton-experimental-gets-dlss-for-dx12-games-on-linux/">DX12</a> steam launch options here <br>
ProtonDB; got some optimisation tips from their <a href="https://www.protondb.com/help/improving-performance">Performance</a> page
