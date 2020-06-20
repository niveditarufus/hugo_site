---
weight: 1
title: "Contribution 6: Crowd Counting From Single View"
date: 2020-06-15T21:54:49+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

I have successfully completed the first milestone of my GSoC which was to count people present in the scene given a video feed using existing deep Net models. In my earlier [post](https://niveditarufus.github.io/posts/comparison/), I had mentioned that I will be going foreward with the SS-DCNet model due the advantages which I had discussed. I have used the models that were trained the Shanghai Dataset(A, B) and QRNF dataset by the authors of the [SS-DCNet paper(ICCV 2019)](https://arxiv.org/abs/2001.01886). This is the link to my [repository](https://github.com/niveditarufus/PeopleCounter-SSDCNet). The inputs are one of the three pretrained models and a video file(which may be a URL or a file stored in the videos folder of the repository). In the event that a video is not not supplied a reference to the webcam will be grabbed.  
{{< figure src="/images/CrowdCountingFromSingleView/example.jpg" title="An example of the of the People Counter employed through SS-DCNet" >}} 

###### Observations:
The SS-DCNet fails sometimes when the number of people in the scene is say 2 or 3 as it is trained on overcrowded datasets. This may resolved if we train the network to perform in the setting in which we want to count the people or have a model that is suited to scarcely populated images whenever the SS-DCNet returns a count less than some given threshold.
This I will try to resolve in the coming weeks on the advise of my mentors.

##### Status: Under Review