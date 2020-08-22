---
weight: 11
title: "SSDCNet vs SSDNet"
date: 2020-06-20T15:27:24+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

In my earlier [post](https://niveditarufus.github.io/posts/crowdcountingfromsingleview/), I had mentioned that the people counter based on the SSDCNet model fails sometimes when the place is very scarcely populated. So I compared its performance with a counter based on the SSDNet model. 
Given below is an example of footage of 18 people ([SALSA dataset](https://tev.fbk.eu/salsa)).
{{< figure src="/images/SSDCNet-vs-SSDNet/SSDCNet.gif" title="With SS-DCNet based counter" >}} 
{{< figure src="/images/SSDCNet-vs-SSDNet/SSDNet.gif" title="With SSDNet based counter" >}} 

We can see that the SSDCNet based counter performs better in comparison with the SSD based approach. SSDCNet is more effective when people are huddled together while SSDNet base approach fails to recognize people. But when the place is scarcely populated(< 3) people are being able to get properly classified, so, SSDNet performs better.

###### Possible solutions to improve the performance of SSDCNet:
1. Train SSDCNet on a similar setting where it needs to be used.
2. Use some filtering techniques to smooth out unrealistic jumps in the no. of people in a continuous video feed.  


##### Status: Under Review