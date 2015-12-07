---
layout:     	post
title:      	PSP linkage global approach
date:       	2015-11-30 12:00
author:     	Marie Dekou
tags:         result
---

Since we are moving towards the end of the project, we think its a good idea to make a last post to clearly define the structure of our problem and present our workflow. 

## Problem definition

We are trying to generate a PSP linkage of the polymer films from the data-set we get. For the process side, we have some process parameters as the density, the film thickness but mostly the bivariate distributions of the films (they characterize the molecular composition of the films).
For the structure, we have the morphological features extracted from the SAXS and WAXS images.
And for the properties, the tear and puncture resistance of the films.

![problem definition]({{ site.url}}/MIC-polymers/img/PCAproblem/last posts/problem definition.png) 

We will extract 3 types of predictive models:
1. A Process-Structure predictive model
2. A Structure-Property predictive model
3. A Process-Structure-Property predictive model of the mechanical properties

## Approach

Our approach is summarized in the following image.

![global approach]({{ site.url}}/MIC-polymers/img/PCAproblem/last posts/workflow.png) 

 The main idea is to:
1. Reduce the space (process or structure variables) using a PCA or a stepwise regression
2. generate the regression models of the mechanicals properties using the chosen parameters
3. performs a LOOCV and compare the criteria to choose the best predictive model.

We will present our results in the final post.

