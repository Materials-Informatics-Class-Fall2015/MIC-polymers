---
layout:     	post
title:      	Going Forward 
date:       	2015-01-01 12:00
author:     	Andrew Castillo
tags:         
---

# The final hurdles
The last problem we faced when approaching the database approach was being able to compare the experimental to simulated images. Normalization may not be obvious since the information is in the fourier space.
Normalization across all of the images by their max value to match the max value of the experimental image was found to distort clustering for volume fraction. Preferrably the variables manipulated would be in real space.
If the mean electron density, as well as difference of electron density could be established, than a range could be applied to the continuous local states of the real microstructures. Other methods may be viable but ultimately
since we are using PCA as a way to inform us of the properties of the microstructure, normalization of the experimental data needs to be approached carefully.

We are comparing images such as the ones below:
[experimental](https://40.media.tumblr.com/c6b7c10260171f9cdeffc8af72f364ac/tumblr_nz7vod2N0J1rlqsr4o1_540.jpg)

[simulated](https://36.media.tumblr.com/35f263541744e1a5ab88d0104f3bb826/tumblr_nz7vokmZ6s1rlqsr4o1_540.jpg)

We ultimately think that varying the range of the electron densities may be the answer. Below shows two plots of a cut in the horizontal direction of simulated scatter images using different ranges of electron density
but with the same overall microstructure. 

[horizontal cut 1](https://40.media.tumblr.com/f4a1fb3d7273ade86ffd6b6d6ca3d653/tumblr_nz7vizHkv41rlqsr4o1_1280.jpg)

[horizontal cut 2](https://40.media.tumblr.com/a2975b66625baca422e2f8152e39b707/tumblr_nz7vipzCyY1rlqsr4o1_1280.jpg)

If we normalize by the max value we see the change in the profile occurs at the same point, however the magnitudes are not the same suggesting simple normalization may not be the answer, which may pose a problem as trying to
make better matches using PCA.

[normalized](https://40.media.tumblr.com/0c51c14823d60d81f99cbd7d0ba26176/tumblr_nz7vjfvs3l1rlqsr4o1_1280.jpg) 


# References & Moving Forward
In an effort moving forward I will provide various resources which we used throughout the semester to better understand scattering in polymers
as well as the data extracted from SAXS and WAXS images. These resources lay a foundation to build upon along with work we have done throughout the project.

## Equations Used
The equations we used throughout the semester to derive the characteristic equation as well as the equations used describe the scattering phenomena are laid out [COMING SOON]()

## Literature review background
For the uninitiated the resources below were of great help when understanding the problem.

Chapter 1 of the paper below provides a great explanation about the physics behind scattering and takes a step by step guide to introducing common equations used throughout
scatter theory and how they relate to the physical phenomena. 
Scattering from Polymers; Cebe, P., et al.; ACS Symposium Series; American Chemical Society: Washington, DC, 1999. ## Background Literature Review

The books below provide a more mathematical approach to scatter theory and have descriptions of 2-phase materials which were useful in first evaluating our initial, direct approach.
For a background in the equations laid out check out pg 41-46 of Structure Analysis by Small-Angle X-Ray and Neutron Scattering, by L.A. Feigin, and D.I. Svergun as well as 
pgs 14-176 of Methods of X-Ray and Neutron Scattering in Polymer Science, R. J. Roe. 

