---
layout:     post
title:      Experimenting with the Data
date:       2015-10-28 12:00:00
author:     Andrew Castillo
---
<!-- Start Writing Below in Markdown -->

#Initial notes
Since our images come from samples with varying thicknesses we have identified multiple methods in the determination of an appropriate scaling factor to apply to the images so we can compare them. We have also identified some correction options that
are applied sometimes in typical scatter analysis. We will first go over methods attempted to properly scale the images, followed by image corrections such as the lorentz correction. 

#Methods
Various corrections that can be done in-situ experiementally such as the background subtraction of noise are corrections we do not have to worry about. 

(1) Dividing by the thickness of the specimen

(2) Dividing by the sum of the raw intensity data

(3) Dividing by the mean of the raw intensity data (representative of the scatter length fluctuation squared) 

Method 1 is a correction often applied to raw intensity data to account for differences in scattering due to thickness of the sample film. Method 2 implies dividing by a value which corresponds to finding the overall scattering power (adding up the intensity cross the entire area). 
Method 3 defines normalization to find a characteristic equation often used in scatter practice. Method 3 is chosen as it correlates to a characteristic equation identified in literature (see porod's invariant or porod's characteristic equation) which links the autocorrelation of the original microstructure, to the inverse fft of the intensity image. 


#Lorentz Correction
Applying a lorentz correction provides another venue for us to explore going forward. The lorrentz correction is typically a correction than is used to account for intensity spread over spheres of different radii.
It is also sometimes used to extract structural information directly from intensity images. In effect, this accentuates the features given by the intensity plot. The correction is applied by finding the scattering angle,
calculating the scattering length $q$ from the equation given below and multiplying the intensity across the image at each point by $4\piq^2$. 

##Raw Image
![Raw Image](https://40.media.tumblr.com/089ac3da40afa8c1732a124ccaf72366/tumblr_nx3jojVxUJ1rlqsr4o1_1280.png)

##Lorentz Corrected Image
![Lorentz Correction](https://41.media.tumblr.com/e3da9e62467c61661b6739f37222e1ed/tumblr_nx3jo0MBMf1rlqsr4o1_1280.png) 


##Sources
[1] R. J. Roe, Methods of X-Ray and Neutron Scattering in Polymer Science, 174-176, Oxford University Press 2000.
