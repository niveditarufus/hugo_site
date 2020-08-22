---
weight: 15
title: "Image Stitching"
date: 2020-07-22T16:48:57+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

In my previous [post](https://niveditarufus.github.io/posts/multi-view-people-counter/), I had mentioned a stitching algorithm that was supposed to be robust and insensitive to illumination changes. In this post, I verify the same. So I have implemented the standalone image stitcher [here](https://github.com/niveditarufus/ImageStitching), where I change the illumination randomly(make the image dark, bright, hazy, etc) to verify the robustness of the stitcher.  
Given below is the result of the stitched video where each frame is randomly subjected to illumination changes (bright, dark, Haze):  
{{< figure src="/images/Image-Stitching/stitchedVideo.gif" title="Stitched Video" >}}  
It can be observed that the stitching Algorithm is immune to these changes and performed well. This can be used in various settings for the people Counter to work properly.

##### Status: Algorithm Verified