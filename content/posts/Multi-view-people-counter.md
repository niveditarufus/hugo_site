---
weight: 1
title: "Contribution 8: Multi View People Counter"
date: 2020-07-10T14:45:47+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

In one of my earlier [posts](https://niveditarufus.github.io/posts/comparison/), I had mentioned the preprocessing step for counting the number of people from multiple partially overlapping views. This step involves stitching of the images together to form a single image which is then passed into the counting module ([code](https://github.com/niveditarufus/PeopleCounter-SSDCNet)). This might result in a performance overhead compared to the normal case, this can be balanced by adjusting the `skip_frames` parameter in the code. The stitching algorithm used here is based on the [publication](http://matthewalunbrown.com/papers/ijcv2007.pdf). Unlike many image stitching algorithms that are sensitive to the order of input images, this method is not only insensitive to the order of the input images but also orientation and illumination changes. 
An example of the same is shown below:  
  
{{< figure src="/images/Multi-View-People-Counter/image1.jpg" title="Image 1" >}}  
{{< figure src="/images/Multi-View-People-Counter/image2.jpg" title="Image 2" >}}  
{{< figure src="/images/Multi-View-People-Counter/stitched.jpg" title="Stitched Image" >}}  

The next step is to pass the stitched image into the counter module along with the SS-DCNet model and a filter method as suited to your requirement. One can immediately spot two obvious issues the preprocessing step, that is the performance overhead which can be overcome by adjusting some parameters and the second one is that this will work only for partially-overlapping views, i.e., the image captured by each camera should consist of the common area as well as some uncommon area. This cannot be applied to images captured from two corners of the room covering the entire room but having two different perspectives.  
Given below is a short demo of this algorithm of counting image from the stitched image.  
{{< figure src="/images/Multi-View-People-Counter/stitched.gif" title="No. of people from the stitched Image" >}}  

##### Status: Under Review