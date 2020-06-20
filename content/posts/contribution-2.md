---
weight: 7
title: "Contribution 2: Fixing import errors"
date: 2020-05-12T21:35:34+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

I found this issue because I was still unable to get the [PeopleCounter](https://github.com/robocomp/human-detection/tree/master/components/peopleCounter) component working. It raised an import error there where some functions imported from the [resources directory](https://github.com/robocomp/human-detection/tree/master/components/peopleCounter/resources), which is outside the working directory. My commit ensures that the python modules are imported properly. I had made a [pull-request](https://github.com/robocomp/human-detection/pull/3) for them the same which is still under review. I will update this post once the status changes.

##### Status: Under Review
