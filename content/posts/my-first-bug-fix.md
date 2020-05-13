---
title: "Contribution 1: My First Bug Fix"
date: 2020-05-12T21:03:58+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

This post is about my very first bug fix in RoboComp's [human-detection repository](https://github.com/robocomp/human-detection). Everybody starts with a very small bug, so did I. I found this issue on March 16(before the student application deadline) when I was trying to get the [PeopleCounter](https://github.com/robocomp/human-detection/tree/master/components/peopleCounter) module working on my PC. I realized that there was a line missing in the config file that hosts the People Server. I also found that a path to `MobileNetSSD_deploy.caffemodel` and `MobileNetSSD_deploy.prototxt` was incorrect which was a very easy fix. I had followed RoboComp's contribution guidelines and made a [pull-request](https://github.com/robocomp/human-detection/pull/2) which was merged the same day:relieved:. This was the story of my very first bug fix.

##### Status: Merged