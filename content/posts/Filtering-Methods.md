---
weight: 12
title: "Contribution 7: Filtering Methods"
date: 2020-06-29T14:55:41+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

This will be my last post for the first phase of my GSoC journey. I had promised to deliver a working module that returns the count of people from a single view through a continuous video feed. From my earlier [post](https://niveditarufus.github.io/posts/ssdcnet-vs-ssdnet/), you might have seen the challenges I had faced and the solutions I had proposed. I had mentioned that use of filtering techniques may help smooth out unrealistic jumps in a continuous video feed, I had resorted to two major methods which proved to improve the performance of the count values return with the SS-DCNet model namely, 
1. 1D Kalman Filter based approach
2. A moving average based approach  

Both these methods can be used depending on the crowd density environment and in some cases, the count value returned by the SS-DCNet is itself pretty much good. I have analyzed both these methods with [SALSA dataset](https://tev.fbk.eu/salsa) which are shown below: 
{{< figure src="/images/Filtering-Methods/KalmanFilter.png" title="Effect of Kalman Filter" >}} 
{{< figure src="/images/Filtering-Methods/MovingAverage.png" title="Effect of Moving Average" >}} 

I have also updated the [code](https://github.com/niveditarufus/PeopleCounter-SSDCNet) which now takes in an extra argument which is the filtering method.  
  
I am truly happy as the first phase of the project comes to a close and I really hope I have been able to do justice to it. Looking forward to the next phase!! :smiley:  

##### Status: Reviewed