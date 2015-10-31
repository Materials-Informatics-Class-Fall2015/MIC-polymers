---
layout:     post
title:      Beam stop revisited
date:       2015-10-29 12:00:00
author:     Andrew Castillo
---
<!-- Start Writing Below in Markdown -->

#Beam stop correction
This post revisits the treatment of the beam stop and how to handle the missing information.

#Information at the beam stop is important
The missing information at the beamstop means missing information in our final statistics of the microstructure. For this reason we will spend some more time implementing ways to fill the gap.
The original image of the beam stop is shown below. We have been able to automate the identification of the beamstop center. We are still working on methods to automate the detection of the rod portion
of the beamstop. Using the Lorentz correction we can actually see the beam stop rod much clearer than in the raw image as shown at the bottom of [this post].
 
##Original Image
![raw](https://41.media.tumblr.com/a58c8052a11017423b5ed6abd361bc5a/tumblr_nx3jobetxX1rlqsr4o1_1280.png)

#First correction
Experimentally the values at the beam stop are swamped by the intensity of the beamstop. Our initial treatment of the image was to identify the beamstop and set the values equal to the maximum intensity in the image. 

##Max Value at beamstop
![Simple correction](https://41.media.tumblr.com/fd61a00131021442d083fa2a2fd9ea6b/tumblr_nx3jox418P1rlqsr4o1_1280.png)

#New Corrections
We have decided to implement a new correction to the beamstop. This correction uses a gaussian fitted to a small window of the raw intensity data close to the beam stop. This will make the data appear to be continuous rather than
disjoint in our current method. We are currently still trying to find a method to automate the detection of the beamstop rod throughout our data.

##Gaussian fit at beamstop
![Gaussian Fit](https://40.media.tumblr.com/b615640477e9d4d355f709e6c6cdbf69/tumblr_nx3jnrI3u81rlqsr4o1_1280.png)

