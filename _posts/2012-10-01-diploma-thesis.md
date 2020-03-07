---
layout: post
title: Efficient data transmission of 3d models and textures
categories:
  - Portfolio
tags:
  - Portfolio
excerpt_separator: "<!--more-->"
---

{% include video.html video-file-name="thesis.mp4" video-style="landscape" %}

This [thesis](https://www.stefanwagner.dev/assets/pdf/cgthesis.pdf) evaluates methods and formats to compress 3D models. Some of those formats achieve a compression ratio of 1 to 2 compared to the GZIP binary format. Those can be used to compress the model and the individual level of details (LOD). The LODs can later be used to generate a progressive preview, while the user is streaming the model. The progressive mesh technique from Hoppe et al. is also evaluated to achieve such a preview without sending additional data. 

The models can also be streamed with the progressive mode of JPEG and PNG by using the image geometry technique. The decode time is a large part of the overall time if the user has a very fast connection, therefore those decode times are measured and compared. The size of the textures is larger than the size of the compressed models, but it isn’t possible to compress them any further without decreasing the quality, therefore a streaming method for the textures which uses progressive JPEGs is evaluated. The last part evaluates the given possibilities to store the downloaded 3D models and textures at the client.

University: [TU Dresden](http://www.inf.tu-dresden.de/index.php?node_id=3316)  
In Cooperation with Crytek GmbH  
 ឵឵
[View Thesis](https://www.stefanwagner.dev/assets/pdf/cgthesis.pdf)