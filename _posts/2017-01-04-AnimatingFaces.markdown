---
title:  "Snaps that chat! : Animating speech in images"
categories: [project]
tags: [homography, animation]
---

The motivation for this project was the talking portraits in the Harry Potter series. Given a photo with a face and a sentence, could we animate the image to utter a sentence? 

We approached the problem in the following manner - 

A sentence is composed of phonemes. The correspondence between phonemes and mouth shapes is many-to-one. For example, the sounds for m, p are different but their mouth shapes are similar. We created a dataset with templates for mouth shapes of some phonemes. 

Given a sentence, we split it into its corresponding phonemes. 

We begin by detecting 68 facial landmarks on the image, using the dlib library. 

![Landmarks](/images/Landmarks.png)

We then find a Delaunay triangulation using the facial landmarks. 

![Triangulation](/images/Triangulation.png)

The pipeline is for the expression cloning is shown below. We impose a few simple rules so that the size of the organs remain the same in the warped image. These help in preserving identity while changing the mouth shapes. 

![Pipeline](/images/Pipeline.png)


Here are a few videos of the results

<iframe width="560" height="315" src="https://www.youtube.com/embed/5x1ycUNSJwQ" frameborder="0" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/fIlvKygmR4Y" frameborder="0" allowfullscreen></iframe>



