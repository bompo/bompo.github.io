---
layout: post
title: Streaming textures with progressive JPEG
categories:
  - Portfolio
tags:
  - Portfolio

excerpt_separator: "<!--more-->"
---

**Examples**

The Examples stream a 2048x2048 (1.5 MB) progressive JPEG assigned to a spinning cube using different methods:

[Streaming using native Image Element (only works in Firefox)](http://bompo.github.com/streamingtextures/streaming_native.html)

[Streaming using native Image Element and 2D Canvas](http://bompo.github.com/streamingtextures/streaming_native_canvas.html)

[Streaming using compiled libjpeg and web workers](http://bompo.github.com/streamingtextures/streaming_worker.html)

[Streaming using compiled libjpeg and web workers with controls](http://bompo.github.com/streamingtextures/streaming_worker_custom.html)

[GitHub project](https://github.com/bompo/streamingtextures)


{% include video.html video-file-name="streaming.mp4" video-style="landscape" %}


**Explanation**

3D models can be compressed with compression formats like [WebGL Loader](http://code.google.com/p/webgl-loader/) or [OpenCTM](http://code.google.com/p/js-openctm/) down to a reasonable file size.
But another big part of a 3D Model are the textures. Those are often larger in file size compared to the compressed models and still have to be transferred before the user can see the 3D model.
The textures are often compressed with [JPEG](http://en.wikipedia.org/wiki/JPEG). It would be possible to further decrease the file size by decreasing the resolution or quality of the JPEG images but this would also decrease the quality overall. Another option left, is to stream those textures and show a progressive preview while streaming. JPEG supports a progressive mode, in which data is compressed in multiple passes of progressively higher detail. This is intended for large images which will be displayed while downloading over a slow connection, allowing a reasonable preview after receiving only a portion of the data.

As the Image element of JavaScript doesn't support the onProgress event we can't simply listening for the progress event. The image has to be transfered with a XHR request which supports this event. The mime type of the request has to be overwritten to allow binary data transport. The binary data of the image has to be encoded with base64 and applied to a texture. While this approach is working in Firefox 12, for some reasons (maybe because of the introduction of libjpeg-turbo) it doesn't work in Chrome 19. See this [code example](http://bompo.github.com/streamingtextures/streaming_native.html) for this approach.

For Chrome it's necessary to render the image into a 2D Canvas element. A typed array can be read out from this canvas element and later be copied to a WebGL texture. The live example can be seen [here](http://bompo.github.com/streamingtextures/streaming_native_canvas.html).

Using this approach it's already possible to stream progressive JPEGs, but the approach also introduces stuttering each time a JPEG image gets decoded. This problem occurs because all operations are executed in the main thread of the application. Even applying the texture in small 128x128 chunks for each frame doesn't remove this stuttering. The decoding of a 2k JPEG image using the Image element takes around 50 ms, this is too much to keep a constant frame rate of 60 fps.

Web workers allow one or more JavaScript threads running in the background. They do not have direct access to the DOM and have to communicate by message passing. As the Image element is part of the DOM it's not possible to directly decode JPEG images using the Image element in a web worker. Instead, the decoding of the JPEG images has to be done completely in JavaScript without using DOM objects. It would be possible to write a custom library that supports the decoding of progressive JPEGs but it's faster to use the project [Emscripten](https://github.com/kripken/emscripten).

Emscripten converts C to JavaScript code using a LLVM bridge. With this tool it's possible to convert the reference implementation library of the [Independent JPEG Group](http://www.ijg.org/).

The converted library can then be used in a web worker. A drawback of this approach is the decoding performance of the converted library. It takes around four seconds to decode a 2048x2048 JPEG image. That's 80 times slower compared to the 50 ms of the native JPEG decoder. But as the decoding process doesn't run in the main thread of the application, the whole application feels overall faster without stuttering. The converted library has a file size of 85 KB (GZIP) which has to be downloaded before the application can decode JPEGs in a web worker. This approach is therefore only useful if the application uses many large JPEGs. The live example can be seen [here](http://bompo.github.com/streamingtextures/streaming_worker.html).

**Summary**

The streaming of progressive JPEG only makes sense if the decoder is faster as the communication link and if there are many large JPEGs to be transfered. With the web worker approach the decoding time for one 2k JPEG image takes around four seconds. If the bandwidth of the communication link is capable of downloading the JPEG in less than four seconds it's better to just download the image without a progressive preview. Further enhancements of the JavaScript engines could speed up the decompression process. Also it could be possible to compile another JPEG decoding library like libjpeg-turbo which performs faster as the reference library. If the stuttering is acceptable for the certain use case (e.c. the scene is mostly static) the approach using the canvas element could also be used. The decoding of a 2k JPEG takes around 50 ms using the native approach. This should be faster than most common connection speeds.