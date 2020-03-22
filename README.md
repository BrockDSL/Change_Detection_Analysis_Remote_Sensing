![DSL Logo][dsllogo]


#  Niagara's Land Cover Change Analysis: An introduction to Change Detection Analysis
Description of contents

### Procedures
Content
Open Envi 5.5. Sofware

Click the 'view button' on the menu bar and select Two vertical views 


> NB: this operation will generate a left view and a right view on the visualization area 


Click on the left view> Go to file> go to the location of the downloaded Remote sensing data> select band 4, band 5, and band 6 of your 1978 landsat data > click open

Also select the right view and repeat the same process you did for step three. Select band 4, band 5, and band 6 of your 1979 landsat data and click open.

**Layer Stacking (Joining of bands)**

For this step  we will like to join the three bands  of each view to get an image for each view.

Click on the left view> at the far right you will see tool bax> below the tool box expand the raster management folder and double click Layer stacking

> Layer stacking  parameters dialogue box pop-up

Click import files > select all the 1978 bands in the select input file(i.e., band 4, band 5, and band 6)

> Hold the Control key and select the three bands and click ok

Choose your output filename as as 1978 stack and click ok.


Repeat the same steps you did for step 7 for the 1979 Landsat image(i.e., band 4, band 5, and band 6)

Choose output filename as 1979 stack and click ok


Go to file and add the niagara regional municipality boundaries to both views. Right click the shapefiles > zoom to layer and uncheck the municipal boundaries shapefile


**Classification**

In this section we would like to use unsupervised classificaton(i.e., classification that allows the computer or software to classifying the land cover inro different land uses without any input of the user).

Go to the tool box and expand the classification folder> expand unsupervised classification.

>Note:Unsupervised classification is where outcomes are based on the software analysis of an image without the user providing sample classes. The computer uses techniques to deteremine which pixels are related and groups them into classes.

Double click K-means

Select 1978 stack in the select input file of the classification input file dialogue box.

Click ok

K-means parameter dialogue box pop-up

Select number of classess as 4> choose output filename as unsupervised 1978 > click ok.

Repeat the same classification process for stack 1979 and name it as unsupervised 1979.

Editing of class names and class colors

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

Select unsupervised 1978(i.e.' K-means 1978 stack) as the 'initial state' image and click ok.

Select unsupervised 1979 (i.e., K-means 1979) as the 'final stage' image and click ok.


Choose your output file name location  > type change detection statistics and click ok.
Change Detection Statistics results pop-up. you can see the percentage change, pixel change and area change (in square metre). you can also save your result as a text file. click file and save.


### Conclusion

Content

### Etc.
 
 
 









<!--- Please use reference style images so that it is easier to update pictures later --->

[dsllogo]: dsl_logo.png
