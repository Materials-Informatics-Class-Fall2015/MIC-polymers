---
layout:     post
title:      PCA results 
date:       2015-10-30 12:00:00
author:     Materials Innovation
tags: 		result
---
<!-- Start Writing Below in Markdown -->

#Goals

The goal of this part of our project is to define predictive models of the polymers films mechanical properties (tear and puncture resistance) from their characteristic dimensions (crystalline structures length, width...)

#Dataset

We will run a PCA analysis on 13 variables (the characteristic dimensions) and 18 samples. So our initial data set is a 18x13 matrix. 

![initial dataset]({{ site.url}}/MIC-polymers/img/PCAproblem/PC_dataset.png)

The point is to detect the few variables that will have the most contributions, in order to reduce the variable space.

#Results

### PC scores

The first 3 components contains 93% of the variance, and the first 5, 98%. 

![PC cumulated variance]({{ site.url}}/MIC-polymers/img/PCAproblem/PCvariance.png)

But we will decide later how many components we want to keep for the linear model for each variables.

### Variables contributions

As for the variables, we plot their contributions along the first 3 components to find the most contributing ones. 
Contribution  along PC1,2 and 3= sum over PC1,2 and 3(variable score*PC eigenvalue)

![Variables contributions]({{ site.url}}/MIC-polymers/img/PCAproblem/VarContributions.png)

Their is no clear most contribution variables. It will be difficult to reduce the space since most variables have almost the most contribution.
We decide to keep the variable space as it is, and later use regression tools to choose the ones we use to predict each mechanical property.

### Next steps

The next step is to generate the predictive models first with the variables and next with the PCs.
