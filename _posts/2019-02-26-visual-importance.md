---
layout: post
title: Visual Importance ML
excerpt_separator: "<!--more-->"
---

{% include video.html video-file-name="instagram_visual_importance.mp4" video-style="landscape" %}

Experimenting with moving images and [visual importance](https://github.com/cvzoya/visimportance). The example shows the Oscar's feed on Instagram. This ML network is trained with eye-tracking heatmaps of UIs. Red shows areas of high interest and blue of low interest. This is quite useful for designing flows within apps.

I applied this to the designs from our app Quizfriends. Looks cool, but it seems like it only learned to highlight high contrast areas. It would be even more useful to know where the user is watching first.

![placeholder]({{site.baseurl}}/assets/images/heatmap_quizfriends.jpg)