---
layout:     post
title:      Image Preparation
date:       2015-09-30 12:00:00
author:     Andrew Castillo
---
<!-- Start Writing Below in Markdown -->

#Initial notes
Our material system of interest is LLDPE which we are exploring the crystallinity. The amorphous and crystalline phases are differentiated by
different scattering length densities for the respective phases. 

#Image Preparation
In order to perform reconstruction we need to first identify the two-point statistics of the autocorrelation in order
to do phase recovery. This requires careful treatment of the data in order to successfully apply our relation from the 
autocorrelation to the two point statistics defined in the post here. (link to post coming)

As a visual aid the basic process is shown below. In this plot we have $\rho(r)$ is the scattering length
density distribution (SLDD) and $I(s)$ is the experimental scatter data we have. We are effectively back tracking to $\Gamma_\rho(r)$ which
is the autocorrelation function of our SLDD. From here we can than find our 2-pt statistics.

#Raw Image
We first start with a raw image

![Raw](https://40.media.tumblr.com/71ab1336244161dbcd9fbc801b8f74a2/tumblr_nve0fcJxiN1rlqsr4o1_540.png) 

#Identify Beam Stop
Now we identify the beam stop. Currently we have not applied any correction for the beam stop and are in the process of determining the best
course of action to account for the beam stop. It is still necessary to identify the beam stop in order to apply symmeterize the image.

![Beam Stop](https://40.media.tumblr.com/c16c4895860750999d9b79e1f8eb53a5/tumblr_nvhsp4diEg1rlqsr4o1_1280.png)

#Symmeterize image

![Symmetry Applied](https://36.media.tumblr.com/8dc8c804df5dc35ad5e7ad2f97334087/tumblr_nvhtj6mwfI1rlqsr4o1_1280.jpg)

#Inverse Fourier Transform
Now that we have working data we can proceed to the first step of finding the autocorrelation of the SLDD by performing an inverse fourier
transform over the data.

![IfftApplied](https://36.media.tumblr.com/c9687eebc4b894c8e075d0638e6822a9/tumblr_nvhticr6zM1rlqsr4o1_1280.jpg)

This is the first step to getting 2-pt statistics. In order to complete the conversion we relate the mean squared fluctuation of scatter length density $/eta_0^2$ and
the volume fraction, $V_1$, found experimentally to $Q$, which represents the total scattering power of the specimen. This is described in detail in the post here (link coming). 
