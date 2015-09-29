---
layout:     post
title:      structure property problem
date:       2015-09-25 12:00:00
author:     Marie Dekou

---
<!-- Start Writing Below in Markdown -->


#Problem Statement:

To quantify the crystalline structure of polyethylene Abhiram Kannan define a procedure to measure the geometrical features
of a lamella (in the crystalline structure. the extracted parameters are  dimension and orientation parameters.

![example of parameters extraxted to quantify the crystalline structure]
({{ site.url }}/MIC-polymers/img/posts/parameters.PNG)

The polymers blown films for packaging application need to possess a combination of flexibility, toughness and ductility.
These mechanical characteristics are most often mesured by two standard characterisation methods: the puncture resistance test 
(to mesure mechanical properties) and the tear resistance test (for the orientational tear property measurement).

#Goal:

Our goal is to find the linkage between the film mechanica properties and their geometrical features.

#Data Set

Here | Samples | Samples characteristics| Dimensionality (Armstrons)|Orientation|Mechanical Properties
|---------|:----------|:----------:|---------:|---------:|---------:|
Number of parameters   |18|  4 |4|8|3

We have 12 geometrical parameters to describe the crystalline structure, and we have to link them to the 3 mechanical
properties mesured.

#structure-property problem Workflow

To tackle this problem we will have to reduce the number of geometrical parameters and find a correlation between the
mechanical properties and the principal geometrical features.

![structure property problem workflow](https://github.com/Materials-Informatics-Class-Fall2015/MIC-polymers/blob/gh-pages/img/posts/sp_workflow.PNG)
