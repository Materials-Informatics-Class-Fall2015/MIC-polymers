---
layout:     post
title:      Working data
date:       2015-09-27 12:00:00
author:     Andrew Castillo

---
<!-- Start Writing Below in Markdown -->


#Microstructure Recontruction:
For the microstructure reconstruction the first hurdle to overcome is the extraction of 2-pt statistics from the SAXS and WAXS data. 
This extraction is based off of the equation shown below.

$$
f^{11}( \pmb x) = \frac{1}{V \eta_o^2} \int I ( \pmb k) e^{-i\pmb k\pmb x} d\pmb k + V_1^2
$$

Where $f^{11}$ is the auto correlation of two states, $V_1$ is the volume fraction, $\eta_o^2$ is the mean square fluctuation of the scattering length density, and $I(k)$ is the intensity of the X-ray signal in fourier space. 
This equation was previously derived by David Brough shown  [here](http://nbviewer.ipython.org/github/phelpsforpresident/MIC-XRD-Polymer/blob/gh-pages/notebooks/Relationship_between_XRD_and_Autocorrelation.ipynb)

There are several things to note about this equation, the most important being it is based on initial, known conditions of the material. A post going more in depth into the equation is coming. The first step in applying the derived equation
is cleaning the SAXS and WAXS images. This involves taking the log, cropping and identifying/translating an origin of the images. A total of 24 images are available for use for reconstruction. 12 images are WAXS images, and 12 images are SAXS. The images
correspond to the initial scattering patterns of 12 blown PE samples. The conditions of the 12 samples are shown below.

![Sample Conditions](https://36.media.tumblr.com/5c1182f554d8d06b3e6716b26fcd4ba2/tumblr_nvdzrzbFaj1rlqsr4o1_1280.png) 

With the given data, Percentage crystallinity provides us the initial volume fraction and the initial thickness is given in microns. These provide the answers to the crucial variables 
in the equation above. The MD Draw ratio pertains to a manufacturing conditions of the fully blown film radius to the pre-blown radius. Finally, unprocessed examples of the SAXS and WAXS images are shown below.

##SAXS Image
![SAXS Example](https://41.media.tumblr.com/71ab1336244161dbcd9fbc801b8f74a2/tumblr_nve0fcJxiN1rlqsr4o1_1280.png) 

##WAXS Image
![WAXS Example](https://41.media.tumblr.com/f118d500e0d41b7e848c722b107fc651/tumblr_nve0fqRuBp1rlqsr4o1_1280.png) 

Initially, microstructure reconstruction will only incorporatate SAXS images based on previous work. The WAXS may be taken into account as the determination on the representation of microstructure due to WAXS images is explored by a project running parrallel to ours.

#PCA on existing microstructure information

Various data relating to the microstructure will be used to correlate the tear and dart data to various sample and microstructure data. The goal is to form a relation similar
to the function shown below.

$$
f(D,T)=g(s,d,o)
$$

Where $D$ is the energy required to rupture a thin film in a Dart Test in accordance to ASTM D4272-14, and $T$ is the performance metric pertaining to the elmendorf tear test (trouser tear test). The $s$ pertains to the sample properties shown in the previous section (~4), $d$ pertains to various linear crystallinity metrics (~4) and $o$ are various crystal orientation metrics (~8).
 



#Sources:

[Data Science Solutions to XRD](http://materials-informatics-class-fall2014.github.io/MIC-XRD-Polymer/)

[1]Structure Property Relationship in Polyethylene Blown Films, Abhiram Kannan

[2]Everything SAXS: small angle scattering patterns collection and correction, Brian Richard Pauw
