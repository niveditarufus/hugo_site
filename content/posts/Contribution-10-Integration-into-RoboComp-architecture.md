---
weight: 1
title: "Contribution 10: Integration Into RoboComp Architecture"
date: 2020-08-10T13:01:51+05:30
draft: false
author: "Nivedita Rufus"
twemoji: true
lightgallery: true

toc:
  auto: false
---

I feel really great as I am almost done with integrating the code into the RoboComp architecture. There are still a few things left like documentation and maybe a little code clean up. Over to the details.  
The ability to configure an application's properties externally provides a great deal of flexibility. One can use any combination of command-line options and configuration files to achieve the desired settings, all without having to modify source code of the application. Ice is a handy tool to use in this respect because at it run time automatically loads a configuration file during the creation of a property set, which is an instance of the `Ice::Properties` interface. So, on the same note, I have created a RoboComp Component [PeopleCounter_SSDCNET]() which uses the SS-DCNet architecture for counting people in a video feed.  
The config file requires 6 parameters to be initialised:  
1. **save_results:** set this to true if you want the output to be saved on the system
2. **filer:** It should be set to one of three options(None, kf(Kalman filter) or mavg(Moving average). This will vary from video to video.
3. **model:** This should set to one of the three options(model1, model2, model3). This will vary from video to video.
4. **skip_frames:** No. of frames that need to be skipped.
5. **stitch:** Set this to true if there are multiple video feeds and you want the count values to be obtained post stitching the videos together. setting this to false will assume majority voting.
6. **video:** Path/URL of videos. You can set this None if you want to start a webcam stream.  
The structure of the code follows the Finite State machine style which can be easily understood with the following diagram:  
{{< figure src="/images/Integration/fsm.png" title="State Transition diagram" >}}  
This style of programming ensures easy upgrades in the future without much rewriting of code. The new blocks can just be plugged into the existing modules. The final result of the People counter working from the RoboComp architecture is given below(Image Source: [SALSA dataset](https://tev.fbk.eu/salsa)).  
{{< figure src="/images/Integration/counting.gif" title=" RoboComp People Counter with SS-DCNet" >}}

##### Status: Under Review