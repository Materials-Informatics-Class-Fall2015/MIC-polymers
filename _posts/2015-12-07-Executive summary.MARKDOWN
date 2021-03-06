---
layout:     	post
title:      	Project executive summary 
date:       	2015-12-07 12:00
author:     	Marie Dekou and Andrew Castillo
tags:         
---

## Project Definition
Use given SAXS and WAXS images to recover the microstructure of a semicrystalline polymer. Than, using parameters previously extraced from SAXS and WAXS images to build a process structure property linkage.

### Polymers and XRD
Small angle x-ray scattering describes microstructural features between 10-1000 angstroms. The material of interest was LLDPE, which is a semi-crystalline polymer. The goal was to observe the crystalline
and amorphous regions using scatter images. X-ray scatter images are the result of the scattering of the incident x-ray by the electrons within the sample into spherical waves that when interfere constructively, 
produce regions of higher intensity.  Fluctuations of electron density throughout the sample produce the patterns observed in scatter images. The idea is that areas of higher electron density were characterized as
semicrystalline, and lower electron density as amorphous. These SAXS images can also be thought of as 2D correlation maps in reciprocal space. 

### Dataset 

We had to work with 3 types of dataset: 

1. First the SAXS (960 x 960 pixels) and WAXS (960 x 1920 pixels) images from 12 different polymers films. 
![SAXS]({{ site.url}}/MIC-polymers/img/posts/SAXS_1_0000.png)
 ![WAXS]({{ site.url}}/MIC-polymers/img/posts/WAXS_1_0000.png)

2. Second, a 18 x 19 excel table that contains  the process parameters, 3 mechanical properties and the morphological features of 18 polymers extracted from the SAXS and WAXS images. See [data extraction from the SAXS and WAXS images](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/11/25/data-extraction-from-the-SAXS-and-WAXS-images/).

3. The  [bi-variate distributions](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/10/30/PCAproblem-workflow-update/) of our polymers samples (4836x4 matrix). These distributions just represent the molecular composition of the polymers at an atomic level. 

We decide to tackle 2 different problems from our initial dataset:

1. Generate a PSP linkage for the polymers films using the 18x19 excel table

2. Recover the polymers microstructure from the SAXS images.

### Challenges with recovery
Attempting to recover the SAXS images proved to be a difficult task. The sources of the obstacles presented were  both experimental as well as conceptual. The SAXS images posed new problems we have
not been familiar with. Throughout the semester we have identified these problems when it comes to microstructure recovery. The main issues are listed below.

1. Partial Information due to Beam stop 
2. Partial "Statistics"
3. Missing phase information (FFT)
4. Normalization of SAXS images to compare to each other
 
## Reconstruction Trials 
### Direct Approach
We had originally were pursuing a method to obtain the 2-pt statistics. Since 2-pt statistics are in real space this would allow us to work with data we were more comfortable with. We have experimented
with a characteristic equation  outlined [here](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/09/29/Derivation-equation/). However, since we were missing information at the beamstop
which prevented us from extracting necessary information to correctly derive this equation. We had tried filling the information at the beamstop with a fit to estimate the necessary information [here](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/10/29/Beam_stop_revisited/)
however after reevaluating the fact that the information was a fourier representation in which all variables were independent, we decided not to go with this route.
Either way, once we obtained the 2 pt statistics we still did not have the phase information for the microstructures. We would need to recover the phase information as well to perform a direct reconstruction.

### Database approach
Faced with incomplete statistics we decided to pursue building another method in order to attempt recovery. This method is referred to as the database method. The idea was to simulate various microstructures and 
attempt to perform a match. The microstructures were modeled using rectangles representing crystalline regions and a figure representing this can be seen [here](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/09/26/Background/).
These microstructures were simulated, and the resulting scatter image was than produced. A comparison between how 2-pt statistics are found from microstructures versus how the scatter images are simulated can be found
[here](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/11/21/What_We_Are_Looking_At/). Using the database approach we built upon the forward problem of recovery, focusing on what we could learn.
We showed that scatter images lose a large amount of variance as a result of the missing statistics. However, using PCA, the scatter images still appear to loosely cluster based on designated parameters. 
This is an important finding as if SAXS experimental images can be compared against simulated images, the closeness to families of clusters can inform the choice of simulated microstructure, giving an iterative process in which
parameters close to those of the actual microstructure can be found.  These findings can be shown [here](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/11/21/Database_Approach/).

## PSP linkage results discussion 

The approach we will be taking is the described in the following image:
![Global approach]({{site.url}}/MIC-polymers/img/PCAproblem/last posts/problem definition.PNG)


This post gives more details about our workflow and the tools we used [PSP linkage global approach](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/11/30/PSP_linkage_global_approach/)

The main criteria we will be using to compare the predictive models are [LOOCV](https://en.wikipedia.org/wiki/Cross-validation_(statistics)) results (Leave one out cross validation) ,the RMPE (Root mean percentage error) and the absolute error percentage.


### Process-Structure Predictive model 

We start by reducing the each bi-variate distribution to one concatenated vector:
![Bivariate plots transformation]({{site.url}}/MIC-polymers/img/PCAproblem/results/bivariate.png)

We then put the 3 vectors in PCA to extract the first component that yield 96% of the total variance (we will call it the bivariate PC). Then we are able to generate some predictive model of the bivariate PC as function of the structure parameters.

![PS results]({{site.url}}/MIC-polymers/img/PCAproblem/results/bivariate_results.png)

We were able to generate 3 accurate models with a low error, that predict the bivariate PC as function of the structure variables. But the model is still based on a small number of data points.

### Structure-Property Predictive model 

The goal is to predict the 3 mechanical properties using our 13 extracted features (see [data extraction from the SAXS and WAXS images](http://materials-informatics-class-fall2015.github.io/MIC-polymers/2015/11/25/data-extraction-from-the-SAXS-and-WAXS-images/) ).

We first perform a PCA on the variables. The results show that the first 4 components yields 97% of the variance. Here we will use the results of the puncture resistance predictive models as an example.
![PCs variance]({{site.url}}/MIC-polymers/img/PCAproblem/results/PCA variance.png) 
![regression results dartdrop]({{site.url}}/MIC-polymers/img/PCAproblem/results/dartdrop_results.png) 
![absolute error]({{site.url}}/MIC-polymers/img/PCAproblem/results/error.PNG). 

For evry single predictive model we have on average a high absolute error. Even with the model using the PCs. It's impossible to reach a good level of accuracy in the Structure-Property linkake because of 3 possible raisons:

1. The dataset is too small to capture enough variance
2. 13 variables are not enough to capture all the informations contained in the SAXS and WAXS data.
3. There is something mising. The SAXS and WAXS are not enough to directly predict the mechanical behavior of the polymers films.

### Process-Structure-Property Predictive model 

Then we want to explore 2 other type of model:
1. Process-Property: Predict the mechanical properties using the process parameters
![PP error]({{site.url}}/MIC-polymers/img/PCAproblem/results/PP_error.PNG)
It's also impossible to accurately predict the mechanical properties using the process parameters and bivariate PC.
2. Process-structure-Property: Predict the mechanical properties using both the structure PCs and the process parameters.
![PSP error]({{site.url}}/MIC-polymers/img/PCAproblem/results/PSP_results.png)

The predictive model is still not accurate, but adding the molecular bivariate component didn't improve the model. 

## Collaboration
We have had several meetings with Dr. Kalidindi in order to develop strategies to approach our problems. Abhiram Kannan provided domain expertise when needed. We also received assistance from Yuksel Yabansu in simulating microstructures.

## Conclusion 
We have identified many of the main issues regard microstructure recovery using SAXS images. We have built upon the forward problem of microstructure recovery. In effect, we laid the foundation for a database approach to be further explored in the future.  We have also built process-structure-property linkages using extracted microstructural information with varying results. Our results from error suggest that the data extracted may have been too severe a data reduction. Future efforts to make such a linkage would require the full use of SAXS and WAXS images.
