---
layout: post
title: Raymarching in WebGL
excerpt_separator: "<!--more-->"
---

![placeholder]({{site.baseurl}}/assets/images/raymarching.jpg)

Once again&nbsp;I&nbsp;used some music by&nbsp;[bitbof](http://twitter.com/bitbof)&nbsp;and synced it to the&nbsp;amazing&nbsp;raymarching examples from&nbsp;[Frank Reitberger](http://www.dasprinzip.com/prinzipiell/2011/02/21/raymarching/).&nbsp;I used some kind of pseudo "beat detection" to detect patterns in the volume changes of the music. Basically it just listens for small, medium and high volume peaks. The volume changes are precalculated with&nbsp;[Mr.doob's python script](http://mrdoob.com/blog/post/677)&nbsp;and included as a large array. The beats are then mapped to the shader variables to alter the torus. If a medium beat or a large beat is detected the shader changes the definition of the implicit torus so that the hole scene looks a bit more dynamic.

[See it live WebGL Demo](http://bompo-blog.appspot.com/webgl/iteration_music/implicit_music.html)