Instructions for test data: 

Test data, movies and code files can be viewed and downloaded at:
https://drive.google.com/drive/folders/1ydiquobUvtjjwF_ZscazSaFLyt7J81TO?usp=sharing


Data set 1(Spheres): artificial beads in 3d
 
In this data set I created a fake image stack of 500 images (Original) and applied intensity gradients:
a) Lin_X - Linear gradient along the X axis up tp 10% intensity loss
b) Lin_XY - Linear gradient along the X and Y axis up tp 5% intensity loss (in the corner)
c) Log_Z - Logarithmic gradient along the Z axis up tp 10% intensity loss
d) Lin _Lin_Log_XYZ - Combined gradients for Lin_XY and Log_Z 

Recommendations of use with Intensify3D; 
a,b,c,d) default parameters - just press GO!


Data Set 2(Example2pImageStack): 2-Photon Imaging of CChIs 

This data was acquired by vivo 2 photon imaging (done by Amir Dudai) with no laser power adaptation.
it contains 271 images going from deep to shallow with 1um step size.
  
Recommendations of use with Intensify3D; 
It's better to go to an image that contains more signal e.g. 100 
and also increase "Spatial Filter Size" to 150 since there are large somata along the stack
for better viewing of data i would recommend applying a 3D gaussian filter (e.g. FIJI)
However!, never filter before normalizing with Intensify3D, Raw data is (almost) always better.

Data Set 3 (IDISCO_brain_Auto_Flou): Light-Sheet imaging of IDISCO mouse brain 
This imaging was done with a La-Vsion Light Sheet Ultra microscope 2 microscope with a GFP Ex/Em filter for auto fluorescence and 10um step size 
scanned medially to laterally. This image stack (400 images) was down sampled 16 fold from 2560x5160 to 640X540 and 3 fold along the Z axis from ~1200 to 400 for easy testing and running. 
Intensify3D is built to handle large data sets and can process the original sized stack as well. 

Recommendations of use with Intensify3D; 
Maximum Background intensity - 6000* 
Normalization Type - Contrast Stretch - see assumptions 
Spatial Filter Size - 50
Automatic Tissue Detection - E.M. with 3.5 Sensitivity 

*Since there is so signal and background defined in this case and our aim is to increase homogeneity we will set a parameter much higher that the brightest pixel. 
Intensify3D will use the max pixel value of each image as reference.  