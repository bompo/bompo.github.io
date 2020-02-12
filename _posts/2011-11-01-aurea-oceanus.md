---
layout: post
title: Aurea Oceanus
categories:
  - Portfolio
tags:
  - Portfolio
excerpt_separator: "<!--more-->"
---

{% include youtube.html video-id="sruGpHp4Ehw" cover-image="aureaoceanus_cover.jpg" %}

I made a underwater surival game. Here is the mini post mortem:

![placeholder]({{site.baseurl}}/assets/images/aureaoceanus_1.jpg)


**What went right**

Framework: I made some games with libGDX before, so this was a good choice for me. I used the experimental model loader extension but besides being experimental everything worked as expected.

Models: I used Blender for the modeling and texturing. All textures are created and baked in Blender. Because of my limited modelling abilities and time constraints the models are kinda low poly but this fits quite well to the overall art style. For the animations of the shark and the seaweed I used a simple wobble vertex shader. This was a huge time saver!

Sound: I recorded the sound effects with my phone or BFXR and added some slomo effects and additional bass with Audacity. This worked quite well. For the music I used some generated tunes of autotracker bottomup and exported them to midi. I imported the midi to LMMS and used a funky synth. Some additional slomo effects in Audacity resulted in the final ambient music.

Mood: FPS + Fog + Sharks + &nbsp;dark ambient sound = WIN!

![placeholder]({{site.baseurl}}/assets/images/aureaoceanus_2.jpg)

**What went wrong**

Game play: The overall game play is to simple. I got no real idea, so I just started a FPS with no real game play target. The initial primary goal was to collect stuff in a limited time constraint. This was to simple, so I added sharks to the game.

Collision detection: Spend way to much time on this one. I did something wrong with the model export. The collision center of all models had a wrong offset… The final collision detection is still kinda hacky in the final entry… :/

![placeholder]({{site.baseurl}}/assets/images/aureaoceanus_3.jpg)

Overall I’m happy with the result. Good mood in the game and I learnt something along the way. See you next time!

### Link
<http://ludumdare.com/compo/ludum-dare-22/?action=preview&uid=7570>

Ludum Dare 48h Combo Entry, Theme: Alone