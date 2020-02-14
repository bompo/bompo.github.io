---
layout: post
title: OpenGL ES 2.0 in LibGDX
excerpt_separator: "<!--more-->"
---

{% include youtube.html video-id="8zyAZvFeeyg" cover-image="opengl_cover.jpg" %}

I played around with the awesome [libgdx](http://code.google.com/p/libgdx/) which makes it possible to develop for desktop and android at the same time. I tried some OpenGL ES 2.0 shader stuff to test the performance. Here are some of the results on a Motorola Milestone with android 2.2.

[Monjori](http://www.pouet.net/prod.php?which=52761)

Shader from mic:

![placeholder]({{site.baseurl}}/assets/images/opengl_1.jpg)

Milestone: ~2 FPS

[Download Jar](http://dl.dropbox.com/u/39448/gdx/monjori.jar)

[Download Apk](http://dl.dropbox.com/u/39448/gdx/monjori.apk)

[Source](http://dl.dropbox.com/u/39448/gdx/monjori_src.zip)

Reflection Mapping of Suzanne (11.000 Vertices)

![placeholder]({{site.baseurl}}/assets/images/opengl_2.jpg)

Milestone: ~30 FPS

[Download Jar](http://dl.dropbox.com/u/39448/gdx/obj_reflection.jar)

[Source](http://dl.dropbox.com/u/39448/gdx/reflectionmapping.zip)

Normal Mapping on&nbsp;

[Lee Perry Smith](http://www.ir-ltd.net/infinite-3d-head-scan-released/)

Head (8.000 Vertices)

![placeholder]({{site.baseurl}}/assets/images/opengl_3.jpg)

Milestone: ~15 FPS

[Download Jar](http://dl.dropbox.com/u/39448/gdx/obj_normalmap.jar)

[Download Apk](http://dl.dropbox.com/u/39448/gdx/obj_normalmap.apk)

[Source](http://dl.dropbox.com/u/39448/gdx/obj_normalmapping_src.zip)

[Video on YouTube](http://www.youtube.com/watch?v=8zyAZvFeeyg)

Results:

*   .obj Loading with libgdx takes a long time (30sec for 8.000 Vertices on a Milestone) &nbsp;
*   complex shaders are too slow&nbsp;