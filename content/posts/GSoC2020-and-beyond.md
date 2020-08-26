---
weight: 20
title: "GSoC 2020 and Beyond"
date: 2020-08-26T17:23:52+05:30
draft: true
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

In the final phase of GSoC 2020, I was given a very interesting problem which was I was done with most of the tasks that I was given: to estimate people's positions using a reference system that originates, for example, from the recording camera itself and also provide an estimate of their orientation. This looks like a simple problem over the top but has its challenges. We would have to do this estimate the pose from a top-down view, i.e. from CCTV footage type videos. 

Here some of my findings, which I have made in this regard:  
Given an image that is most likely from an overhead view, there are no existing pre-trained models to determine the pose of a people in the scene accurately. The approach that may work or is to retrain the network from scratch with images suited to us and see if the model we got works well. The following are the codes which I have tried:
1. [OpenPose code](https://github.com/CMU-Perceptual-Computing-Lab/openpose) [[Publication](https://arxiv.org/abs/1812.08008)]: Works well for 2D pose estimation on the front views. 3D pose estimation can be done by triangulation from multiple views.  
2. [AlphaPose code](https://github.com/MVIG-SJTU/AlphaPose) [[Publication](https://www.mvig.org/research/alphapose.html)]: Works well for 2D pose estimation on the front views. Achieve better mAP than OpenPose. 3D pose estimation is underway.
3. [3D pose estimation code](https://github.com/Daniil-Osokin/lightweight-human-pose-estimation-3d-demo.pytorch) [[Publication1](https://arxiv.org/pdf/1811.12004.pdf), [Publication2](https://arxiv.org/pdf/1712.03453.pdf)]: Gives the 3D pose of people in the world frame if the camera extrinsics are specified.
All these above-mentioned models need to be trained from scratch for images that are suited to our application.
This [repository](https://github.com/facebookresearch/DensePose) is also a suitable candidate in the same field but I have not been able to test it to give enough insights for it.  

Retraining the existing models with some parameter changes would be a very interesting thing to checkout and see if it serves our purpose.  

##### Status: Hopeful:relieved:
