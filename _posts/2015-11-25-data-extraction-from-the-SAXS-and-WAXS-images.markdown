---
layout:     	post
title:      	Data extraction from the SAXS and WAXS images
date:       	2015-11-25 12:00
author:     	Marie Dekou
tags:         
---

##Goal of the post

The second part of our project is about generating a PSP linkage of the polymers films. We had a lot of questions about how the characteristics dimensions in our data-set have been obtained and how they rare related to the SAXS and WAXS images.

![PC-dataset]({{ site.url}}/MIC-polymers/img/PCAproblem/PC_dataset.png)

The variables from the morphological domain are quantified from the X-ray scattering measurements.They are  the dimension parameters and orientation parameters of crystalline and non crystalline
components of the semicrystalline morphology of films at the atomistic scale (1-10 °A)
and the mesoscopic scale (10-1000 °A).

Processing techniques enable the conversion of 2D data to the more useful 1D data. An integral aspect of this conversion and one that is routinely utilized in both SAXS and WAXS data is the extraction of line profiles
from the 2D data.

### From the SAXS images 

Here are 3 examples of how this characteristics features can be extracted using line cuts. 

![dac]({{ site.url}}/MIC-polymers/img/PCAproblem/last posts/dac.PNG) 
![Lsaxs]({{ site.url}}/MIC-polymers/img/PCAproblem/last posts/Lsaxs.PNG) 
![tilt angle]({{ site.url}}/MIC-polymers/img/PCAproblem/last posts/tilt angle.PNG) 

### From the WAXS images 

The extraction of percentage crystallinity from 2D WAXS data is possible by evaluating the
ratio of peak areas of the crystalline peaks and the total area under the scattering curve.
This is conventionally achieved by first obtaining 1D line cuts of the circularly averaged 2D
data and subsequently subjecting the line cuts to profile fitting. The line cuts are expected
to contain crystalline peaks distributed over a broad amorphous scattering.

An analysis of Herman’s orientation parameters from the WAXS data quantifies the relative
orientations of the normals to the hkl planes in the system i.e. normals to the 110 and 200
orthorhombic crystal planes.

### Sources

[1]Abhiram Kannan thesis dissertaion: Structure Property Relationships in Polyethylene Blown Films.
