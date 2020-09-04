---
layout: post
title: SQIN Face Scanner
excerpt_separator: "<!--more-->"
---

{% include video.html video-file-name="sqin_face_shape_scanner.mp4" video-style="portrait" %}

We have developed a face scanner that can recognize features of the user's face. 
To do that we have written a plugin for Unity that uses Tensorflow lite to extract the 3d information of the user's face. The technology is based on the work from [Mediapipe from Google](https://google.github.io/mediapipe/solutions/face_mesh.html).
This solution works in the editor and on mobile devices as well which do not natively support ARKit or ARCore.

{% include video.html video-file-name="sqin_ar_in_unity.mp4" video-style="landscape" %}

[Try it out!](https://sqin.app/)