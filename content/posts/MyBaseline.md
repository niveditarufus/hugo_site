---
weight: 8
title: "Contribution 5: My Baseline"
date: 2020-06-01T15:44:26+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

The project phase has started. I have made a standalone standalone python project to count people which will be my baseline to test different methods. You can find it [here](https://github.com/niveditarufus/People_counter). This is a refactored version of the existing [PeopleCounter](https://github.com/niveditarufus/human-detection/tree/master/components/peopleCounter) module of RoboComp. Once, the most suited method is chosen, I will integrate it with RoboComp architecture which forms the final stage of the project.  

{{< figure src="/images/MyBaseline/demo.gif" title="A short demo" >}}  
So there, two ways to count people inside a building:  
**1. Tracking people entering and exiting the building:**  
This is possible when we have cameras at the entrances to the building.  
**2. Keeping a running count of people in each room of the building:**  
This is possible when the cameras are placed facing the inside of the room, And the number of people inside the building is given by the sum of the count in all rooms of the building.  

So, it depends on where cameras are placed. We immediately can see the problem with the second option, which is the feasibility of placing the cameras facing the interior of the of all rooms, whereas the first option seems to be a viable option which can be extended even to very large-sized buildings provided we have cameras at every entrance. 
In my earlier [post](https://niveditarufus.github.io/posts/project-phase/), I had mentioned the methods:
1. [Deep-SORT](https://arxiv.org/pdf/1703.07402.pdf)
2. [CSRNet](https://arxiv.org/pdf/1802.10062.pdf)
3. [SS-DCNet](https://arxiv.org/pdf/2001.01886.pdf)
On analyzing these techniques, It can be seen that the first approach can be used in case of the first scenario, where we have cameras at entrances. While the next, two approaches are more suited to the second scenario.
I intend to use the Deep SORT approach and see whether it is able to perform better than the current baseline which uses the MobileNet SSD model. 

##### Status: Still Excited :joy::joy: