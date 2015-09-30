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
autocorrelation to the two point statistics defined in the post [here](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/09/29/Derivation-equation/).

As a visual aid the basic process is shown below. In this plot we have $\rho(r)$ is the scattering length
density distribution (SLDD) and $I(s)$ is the experimental scatter data we have. We are effectively back tracking to $\Gamma_\rho(r)$ which
is the autocorrelation function of our SLDD. From here we can than find our 2-pt statistics.

![Visual Aid](https://41.media.tumblr.com/b00fe6a64ecfdb89feb1422f6600e1ce/tumblr_nvhw1d6uuh1rlqsr4o1_400.png)

#Raw Image
We first start with a raw image

![Raw](https://40.media.tumblr.com/71ab1336244161dbcd9fbc801b8f74a2/tumblr_nve0fcJxiN1rlqsr4o1_540.png) 

#Identify Beam Stop
Now we identify the beam stop. We are in the process of determining the best course of action to account for the beam stop. For now we will apply the max intensity to the beam stop area. 
It is still necessary to identify the beam stop in order to apply symmeterize the image.

##Original Beam Stop
![Beam Stop Raw](https://40.media.tumblr.com/c16c4895860750999d9b79e1f8eb53a5/tumblr_nvhsp4diEg1rlqsr4o1_1280.png)

##Corrected with Max Intensity Method
![Beam Stop Corrected](https://40.media.tumblr.com/de37fe07fbfcb6e3cc2d5aab0f475a64/tumblr_nvi05pXA2j1rlqsr4o1_540.jpg)

#Symmeterize image
Now after we have identified the beam stop we will apply symmetry to the image. Note: the image below does NOT have the corrected beam stop.
![Symmetry Applied](https://36.media.tumblr.com/8dc8c804df5dc35ad5e7ad2f97334087/tumblr_nvhtj6mwfI1rlqsr4o1_1280.jpg)

#Autocorrelation
Now that we have working data we can proceed to the first step of finding the autocorrelation of the SLDD. The result is shown below.

![IfftApplied](https://40.media.tumblr.com/fa103e0cddf2ee996d613a1284a4f6c3/tumblr_nvi06aaikw1rlqsr4o1_540.jpg)

This is the first step to getting 2-pt statistics. In order to complete the conversion we relate the mean squared fluctuation of scatter length density $/eta_0^2$ and
the volume fraction, $V_1$, found experimentally to $Q$, which represents the total scattering power of the specimen. This is described in detail in the post [here](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/09/29/Derivation-equation/). 

##Sources
[1] R. J. Roe, Methods of X-Ray and Neutron Scattering in Polymer Science, 174-176, Oxford University Press 2000.
