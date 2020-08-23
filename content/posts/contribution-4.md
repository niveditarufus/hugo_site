---
weight: 6
title: "Contribution 4: Porting to Python 3 and and other changes"
date: 2020-05-17T15:02:35+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---


After considering declining support for Python 2 programming language and added benefits from upgrades to Python 3, it is always advisable for a developer to select Python version 3. So, from the statement above, it is pretty much obvious that the first task assigned to me was porting the [People Counter](https://github.com/robocomp/human-detection/tree/master/components/peopleCounter) module from Python 2 to Python 3 which is done.
Changes made are:
1. Changed all print statements from `print " "` to `print()`.
2. Python3 uses the module `queue` and not `Queue`.
3. In Python 3 there are two different types of strings:
 	* The bytes type:  
 	 	This is just a sequence of bytes, Python doesn't know anything about how to interpret this as characters.
	* The str type:  
		This is also a sequence of bytes, but Python knows how to interpret those bytes as characters.
	So, to conversion of an empty string into bytes, can be done with  
	`msg = bytes('', encoding = 'utf-8')`

In this process I learned that due to significant refactoring done in the latest version python [openpifpaf library](https://github.com/vita-epfl/openpifpaf) some functions also need to be changed accordingly in our component. So, I have made the component work with the openpifpaf library version = 0.10.1. The changes I needed to make were:
1. I had to change the line:  
`processed_image_cpu = transforms.image_transform(image.copy())`  
in [specificworker.py](https://github.com/robocomp/human-detection/blob/master/components/openpifpafserver/src/specificworker.py) to:  
`processed_image_cpu, _, __ = transforms.EVAL_TRANSFORM(image_pil, [], None)`  
because `image_transform` is no longer in `openpifpaf.transforms.` because of the version update of OpenpifPaf Library.  
2. I also had to convert the image to a PIL image before passing it through the function mentioned above from a CV2 image as the function only accepts PIL image with the following: 
`image_pil = PIL.Image.fromarray(image)`  

There were also a few very minor bugs which I fixed. So Now the component is up and running and I have made [Pull-request](https://github.com/robocomp/human-detection/pull/5) for the same, do check it out!!!

##### Status: Under Review
