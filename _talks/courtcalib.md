---
title: "Automatic Calibration of Tennis Court Images"
collection: talks
permalink: /kala/courtcalib
order: 3
---

This project was done during my internship at PlaEye LLC. One of my proudest work!!
#ClassicalComputerVision


**As the work was completed during an internship, the key novelty of the algorithm has been redacted, with a primary focus on presenting its outputs below.**

Court Calibration: Establising correspondence between court images and a standard 
court model to further estimate unknown points in the image

The flowchart below depicts the procedural flow for court calibration. 

![image info](../../images/courtcalib_flow.png)

Results
===

The figure below presents the calibrated court image, with the court accurately estimated and highlighted by blue lines.

![image res](../../images/courtcalib_out.png)


There are other special cases as well where the camera is partially covering 
the court. For such occluded and extreme cases, all the current approaches at the time of this project, fails.  

To address this problem, we utilized the concept of cross ratio, specifically its property of remaining invariant under perspective projection.
With the additional feature points derived from the cross ratio, the results obtained are as follows.

![image res](../../images/courtcalib_out2.png)