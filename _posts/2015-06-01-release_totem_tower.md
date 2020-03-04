---
layout: post
title: Totem Tower
categories:
  - Portfolio
tags:
  - Portfolio
excerpt_separator: "<!--more-->"
---

{% include youtube.html video-id="EMLplfjU9aU" cover-image="totemtower_cover.jpg" %}

> **Enter the world of Totem Tower and defeat your opponents!**
>
> * Play against FRIENDS via Google Play Games... 
> * … or compete ONLINE against players from around the world!
> * Experience action packed moments against an opponent in TOWER MATCH, whether AGAINST EACH OTHER ON ONE DEVICE or ONLINE
> * Set a time in the turn-based TIME TOWER mode and challenge your friends!
> * Compete with your daily highscore in CHALLENGE mode against players from around the world!
> * Train your skills against A.I. in the TUTORIAL mode before you compete ONLINE against real players!

{% include video.html video-file-name="totem_tower_battle.mp4" video-style="landscape" %}

We just released our newest game [Totem Tower](https://play.google.com/store/apps/details?id=de.kapitaene.totem)
for Android. 

This is our first multiplayer game. It uses Google Play Games as a framework. This made matchmaking very easy. The biggest challenge was the synchronization between the players who found the match first. As there is no separate game server we needed a local solution. We solved this by keeping two separate local timers on each device. The conflict on who matched first is then resolved between the devices itself.

{% include video.html video-file-name="totem_tower_matchmaking.mp4" video-style="landscape" %}

The game also includes a simple league system. You can rank up if you win multiple games. This influences the matchmaking system as well.

The game was featured on Google Play as Indie Game highlight.


{% include video.html video-file-name="totem_tower_result.mp4" video-style="landscape" %}