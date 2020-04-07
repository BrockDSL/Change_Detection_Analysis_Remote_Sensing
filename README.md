![DSL Logo][dsllogo]


#  Niagara's Land Cover Change Analysis: An introduction to Change Detection Analysis
Description of contents

### Procedures
Content
Open Envi 5.5.3 Sofware

Click the 'view button' on the menu bar and select Two vertical views 
Altenately hold Alt + 2.


> NB: this operation will generate a left view and a right view on the visualization area 


Click on the left view> Go to file> go to the location of the downloaded Remote sensing data> select band 3, band 4, and band 5 of your 1987 landsat data > click open

Alternately you can hold Ctrl +O

Also select the right view and repeat the same process you did for step three. Select band 3, band 4, and band 5 of your 2002 landsat data and click open.

**Layer Stacking (Joining of bands)**

For this step  we will like to join the three bands  of each view to get an image for each view.

Click on the left view> at the far right you will see tool bax> below the tool box expand the raster management folder and double click Build Layer Stack.

> Layer stacking  parameters dialogue box pop-up

Click on the three dot in the box at the right side of the input raster box > select all the 1987 bands in the select input file(i.e., band 3, band 4, and band 5)

> Hold the Control key and select the three bands and click ok.

Choose your output filename as as 1987 Stack and click ok.


Repeat the same steps you did for step 7 for the 2002 Landsat image(i.e., band 3, band 4, and band 5)

Choose output filename as 2002 Stack and click ok.


Go to file and add the niagara regional municipality boundaries to both views. Right click the shapefiles > zoom to layer and uncheck the municipal boundaries shapefile
select the left view> click file> select open> go to the Change Detection Folder> in the Niagara open data fold choose municipal boundary (1) folder> select municipal boundary.shp > click open.

Right click on the municipal boundary.shp in the layer manager and select Zoom to layer Extent.

Select the right view and repeat the above steps to add the municipal boundary shapefile. However, for thsi step you would choose municipal boundary (2) folder and select municipal boundary.shp and click opem. 

Right click on the municipal boundary.shp in the layer manager and select Zoom to layer Extent.

**Subsetting  Stack Data from Region of Interest(ROI)**

Select the left view
Go to the search tool box and search my typing subset in the box> Double click Data from ROIs

Select Input File to Subset Via ROI dialogue box pops-up> For the select input file> Select 1987 Stack > Click ok.

Spatial Subset Via ROI parameters dialogue box pops-up> Select the municipal boundary.shp (i.e., the one at the bottom). 
Choose filename and Save as 1987 Subset> Click open > Cick ok.


With the exception of 1987 Subset, uncheck all other layers in the left view in the layer manager.

Repeat the same process of subsetting data for the 2002 Stack image in the right view.
Select the right view> for the select input file> Choose 2002 Stack and Click ok.
For the Spatial Subset Via ROI parameters  choose the municipal boundary.shp (i.e., the one at the top)
Choose 2002 Subset as the output file name> Click ok.

Also, with the exception of 2002 Subset, uncheck all other layers in the right view in the the layer manager.

**Classification**

In this section we would like to use unsupervised classificaton(i.e., classification that allows the computer or software to classifying the land cover inro different land uses without any input of the user).

Click on the left view> Go to the tool box and expand the classification folder> expand unsupervised classification.

>Note:Unsupervised classification is where outcomes are based on the software analysis of an image without the user providing sample classes. The computer uses techniques to deteremine which pixels are related and groups them into classes.

Double click K-means

Select 1987 stack in the select input file of the classification input file dialogue box.

Click ok

K-means parameter dialogue box pop-up

Select number of classess as 3> choose output filename as unsupervised 1987 > click ok.

Repeat the same classification process for stack 2002 and name it as unsupervised 2002.

*Editing of class names and class colors*
Class Name |	Class color | New Class Name  | New Class Color
--- | --- | --- | ---
Class 1 |	Red | WaterBody | Blue
Class 2 |	Green | Human settlement |Yellow
Class 3 |	Blue | Bareland | Green

Right click on the K-means classes on the left view and select edit class names and colors

Edit class names and colors dialogue box pop-up

Move to class names> click on class1 and type the name fishing activity as the name in the edit box.
with the tables as guide repeat the same renaming process for the other classes.

Move to class color> click on the class name and change the color by double clicking on the color beside the class name(use the above table as a guide).
Follow the same step to change the colors of the remaining classes using the table as a guide

Click ok when you are done with the editing



Repeat this step for the unsupervised 1979 image on the right view



**Change Detection Analysis**

Go to the tool box > expand the change detection folder

Double click change detection statisrics

Select unsupervised 1987(i.e.' K-means 1987 stack) as the 'initial state' image and click ok.

Select unsupervised 2002(i.e., K-means 2002) as the 'final stage' image and click ok.


Choose your output file name location  > type change detection statistics and click ok.
Change Detection Statistics results pop-up. you can see the percentage change, pixel change and area change (in square metre). you can also save your result as a text file. click file and save.


### Conclusion

Content

### Etc.
 
 
 









<!--- Please use reference style images so that it is easier to update pictures later --->

[dsllogo]: dsl_logo.png
