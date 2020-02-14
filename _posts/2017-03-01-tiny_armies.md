---
layout: post
title: Tiny Armies
categories:
  - Portfolio
tags:
  - Portfolio
excerpt_separator: "<!--more-->"
---

{% include youtube.html video-id="rhLI2zwYeEQ" cover-image="tinyarmies_cover.jpg" %}

{% include video.html video-file-name="tinyarmies_game.mp4" video-style="landscape" %}

> A new era has begun. Fight for ultimate supremacy in Tiny Armies: Clash Arena, where players from around the world take part in massive, epic multiplayer battles.
> Recruit soldiers, capture bases, and grow your army into a formidable force with skull-crushing giants and fire-breathing dragons - all live and in-play.
>Become the most feared warrior on the battlefield and destroy your enemies! Choose your hero, battle in bustling arenas across the kingdom, and earn awesome bonuses by taking on exciting live missions!

Tiny Armies was our second big game after Hi Frog!. It took nearly 3 years of development and was our first game with an external publisher. It got featured as an early access title on the Android Play Store.

We did serveral new things in this game. The biggest challenge was the implementation of a 8 player real time multiplayer mode. We choosed [Photon](https://www.photonengine.com/) as a multiplayer framework. It took serveral optimizations to keep the transmission package size small and ensure a smooth playback even on 3G devices.

The game also features a league system. This rewards and engages good players to rank up. Its also used as a fair match making system to ensure that verteran players get matched.

![placeholder]({{site.baseurl}}/assets/images/tinyarmies_assets.jpg "Assets")

We put great effort into a fair free to play system. This meant several redesigns of the entire monetization system. The whole system was driven by a strong analytics backend which ensured that development goes into the right direction.

{% include video.html video-file-name="tinyarmies_menu.mp4" video-style="landscape" %}


**Play** 
<https://play.google.com/store/apps/details?id=com.playstack.tinyarmies>