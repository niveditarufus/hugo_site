---
weight: 1
title: "Contribution 9: Majority Voting"
date: 2020-07-28T12:21:44+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

This is my last contribution to the second phase of my GSoC journey. Here, I have implemented the [Boyer-Moore Majority Vote algorithm](https://www.cs.utexas.edu/~moore/best-ideas/mjrty/) for video feeds from multiple cameras from different perspectives, i.e. for views shown below. (Image Source: [SALSA dataset](https://tev.fbk.eu/salsa)) 
{{< figure src="/images/MajorityVoting/cam1.jpg" title="Camera: 1" >}}  
{{< figure src="/images/MajorityVoting/cam2.jpg" title="Camera: 2" >}}  
{{< figure src="/images/MajorityVoting/cam3.jpg" title="Camera: 3" >}}  
{{< figure src="/images/MajorityVoting/cam4.jpg" title="Camera: 4" >}}  

As visualized from these images, stitching is not possible in this case as their perspectives are different. The Boyer-Moore Voting algorithm is briefly discussed here. This algorithm is O(n) in time and O(1) in space. The variables involved are a *current majority vote* and a *current majority vote counter*. These will be initialized to None/Null and 0 respectively. To find the majority vote, we iterate through each vote in the votes list. For every vote, we compare it to the current majority. If the counter is 0, we replace the current majority with the current vote. If the current vote matches the current majority, we increment the counter, otherwise, we decrement the counter.  
This algorithm is implemented on the count values returned by the SS-DCNet Counter for each of the different perspective views to return the count value that forms the majority. If there is no clear majority, the element with the maximum count is returned and if all the elements are unique, the average of all count values is returned.  

#### A demo of results for the multiview People counter
Given below is the case when stitching is not possible, i.e. the different perspective views. This is the video of 18 people the [SALSA dataset](https://tev.fbk.eu/salsa)containing 4 perspectives(shown above) and the final count is returned through the majority voting algorithm of the views.  
{{< figure src="/images/MajorityVoting/mv.gif" title=" Camera:1 view with the count value returned through majority voting" >}}  

Given below is the results of the case when image stitching is possible and the count of the people is returned after merging the images:
{{< figure src="/images/Multi-View-People-Counter/image1.jpg" title="Image: 1" >}}  
{{< figure src="/images/Multi-View-People-Counter/image2.jpg" title="Image: 2" >}}  
{{< figure src="/images/Multi-View-People-Counter/stitched.jpg" title="The Stitched Image" >}}  

{{< figure src="/images/Multi-View-People-Counter/stitched.gif" title="No. of people from the stitched Image" >}}  


##### Status: Under Review