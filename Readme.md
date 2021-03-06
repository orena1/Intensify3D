# Intensify3D - Normalizing 3D Image Stacks

## Installation instructions
 Two options exist to use intensify3D 
1)	For MATLAB users:
Clone or Download the source code, set the MATLAB_Code directory as the current working directory and run file:  User_GUI_Intensify3D.m

 
2)	For standalone:
Download the latest version of the compiled code which fits your operating system:
https://github.com/nadavyayon/Intensify3D/releases 
After installation, execute Intensify3D

 
Follow instruction bellow as well as test data instructions.
## Graphical user interface (GUI) Manual. 

Before starting please read the manuscript and make sure the assumptions of normalization are met. Intensify3D can correct an unlimited number of images since it operates in a serial manner. Hence, it only supports image sequences. However if your image stack is in multi-Tiff format there is an option in the GUI to convert the file to individual images. The *.tif files should ideally be unprocessed data in a 12 or 16bit format. Memory requirements depend on image size and parallel processing. Based on our experience, the maximum requirements are 750 bytes/pixel. Thus, processing a single Light-Sheet image of 2560x2160 pixels will require ~ 4Gb of RAM from each processor + 4Gb for general processes. For example, if your PC has 4 cores, it is possible to analyze 4 Light Sheet images simultaneously, which will require 20Gb of RAM. It is highly recommended to start with a few representative images (~20), adjust the parameters and only then run the process on the entire stack.

![Alt text](Figs/Figure_S1-01.jpg?raw=true "Optional Title")

### Operation instructions and GUI options:

a. The graphical user interface is divided to 3 panels:
* Panel 1 – Folder or file selection: Here the user selects the directory containing the individual images in the stack in TIFF format. Alternatively, if the images are in multi-TIFF format, the user should select the “browse file” option and the multi-Tiff will be converted to multiple file form in a directory carrying the file name.

* Panel 2 – Estimate your background: The objective of this section is to assist the user to select the ideal maximum background intensity (MBI) in a single image. This value will be used by Intensify3D to estimate the background across all images in the stack. “Image number to display” is used to select a representative image from the stack that carries a clear signal. Once the image has been selected, pressing the “show image and estimate parameters” button displays the requested image is displayed, a brightness contrast adjustment window opens (b) and an initial estimation of the MBI is assigned based on the 100th percentile of intensity potentially showing only signal pixels in red. Next, the user should adjust the MBI selection with the dedicated slide bar at the bottom of the image in the following order: (1) adjust brightness and contrast (2) move slide bar to set MBI (performing 2 before 1 will show a distorted selection of the MBI). Repeat 1->2 until satisfied with the result*. The matched value for the MBI will be set in the “stack parameters” section in panel 3.

* Panel 3 – Setting run parameters: The parallel processing section very useful when analyzing large image stacks. The GUI detects how many cores your CPU has and offers the user the option of how many of them will be dedicated to the run. If your MATLAB license does not include the parallelization package, select 0 and work without it (this limitation does not apply to standalone version). The “stack parameters” section defines the first and last image that would be processed in the stack, the MBI (described above) and the spatial filter size. Spatial filter size determines the frequency of intensity changes that would be corrected by Intensify3D. The minimum value for this parameter should be a least twice to diameter of the largest signal structure. Lower values could affect the signal. “Z normalization type” section allows section of the desired normalization type across the images in the stack (for more information see main text and supplementary figure S3).  Last, Intensify3D has the ability to detect the background or tissue area in an image based on 2 clustering algorithms: K means and Expectation Maximization (E.M.). This option should be explored for images where not all the image area is relevant for normalization and is critical in such images. The sensitivity of the tissue detection should be experimented by the user to fit to the specific image set (for more information see main text and supplementary figure S4).     

Last, after running Intensify3D, The “Start” will change to messages regarding the run progression.

*intuition for selection of the MBI value: The correct approximation of the image background depends on “cleaning out” the signal pixels by thresholding and spatial filtering. High brightness signal pixels can affect the ability of the spatial filter.  The MBI should be set so that the most signal pixels will be removed without removing background pixels. Notice the red-labeled pixels in the example image of bright spheres. Lowering the MBI would result in removing background pixels and increasing the MBI would retain more signal pixels. Both ways will lead to a sub-optimal estimation of the background. 



 All rights reserved. No part of this software may be reproduced, 
 distributed, or transmitted in any form or by any means, including photocopying,
 recording, or other electronic or mechanical methods,
 without the prior written permission of the publisher,
 except in the case of a citation and certain other
 noncommercial uses permitted by copyright law.

