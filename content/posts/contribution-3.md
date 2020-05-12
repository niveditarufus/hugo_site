---
title: "Contribution 3: Fixing default parameter values"
date: 2020-05-12T21:51:16+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

I had submitted a [pull-request](https://github.com/robocomp/human-detection/pull/4) to update the file [specificworker.py](https://github.com/robocomp/human-detection/blob/master/components/openpifpafserver/src/specificworker.py) in the component [openpifpafserver](https://github.com/robocomp/human-detection/tree/master/components/openpifpafserver). These added lines are some parameters which are in the [file](https://github.com/vita-epfl/openpifpaf/blob/master/openpifpaf/network/nets.py) and not specifying these values lead to Attribute errors. I initialized all these parameters to the default values specified in the [openpifpaf package](https://github.com/vita-epfl/openpifpaf). I belive this should solve the issue. 
This pull-request is still under review an I will update the post when the status changes.