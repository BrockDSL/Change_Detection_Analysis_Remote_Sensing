![DSL Logo][dsllogo]


#  Niagara's Land Cover Change Analysis: An Introduction to Change Detection Analysis

### Introduction

For this project, I will explore Landsat images using ENVI 5.5.3 to identify changes in land cover between 1987 and 2002 in the Niagara Region. Data for the purpose of this project were gathered from United States Geological Survey (USGS)EarthExplorer and the Niagara Open data websites. data retrieved from USGS EarthExplorer website were Landsat 5 and Landsat EMT7 images for the years 1987 and 2002 respectively. The Niagara Open Data website provided my study with boundary shapefiles for the Niagara Region and St. Catharines. I collected the boundary shapefile  for St. Catharines because I had wanted to understand changes in land cover at the individual municipality level rather in addition to the entire region.Furthermore since I am staff at Brock University which is also located in St. catharinees, thus findings of land cover change in St. Catharines will be of benefit to environmental researchers at Brock, environmental activists, authorities at the St. Catharines' Municipality and in particular the Niagara Region Municipality at the larger scale. 

### Procedures

Download the Change Detection compressed folder from the GitHub link below:
https://github.com/BrockDSL/Change_Detection_Analysis_Remote_Sensing

Locate the downloaded file on your computer. Right-click the file and extract it to a location where you can easily find it, such as your Documents folder.

Open Envi 5.5.3 Software


 ![Envi 5.5.3 Visualization view][logo31]


Click the 'view button' on the menu bar and select Two vertical views 
Altenately hold Alt + 2.


 ![Two Vertical Views][logo2]


> NB: this operation will generate a left view and a right view on the visualization area 


Click on the left view> Go to file> go to the location of the downloaded Remote sensing data> select band 3, band 4, and band 5 of your 1987 landsat data > click open


![Loading of 1987 bands][logo24]


Alternately you can hold Ctrl + O

Also select the right view and repeat the same process you did for step three. Select band 3, band 4, and band 5 of your 2002 landsat data and click open.


![Loading of 2002 bands][logo25]



**Layer Stacking (Joining of bands)**

For this step  we will like to join the three bands  of each view to get an image for each view.

Click on the left view> at the far right you will see tool box> below the tool box expand the raster management folder and double click Build Layer Stack.


![Raster management folder showing layer stack][logo18]


> Layer stacking  parameters dialogue box pop-up


![Layer Stack Dialogue box][logo19]


Click on the three dot in the box at the right side of the input raster box > select all the 1987 bands in the select input file(i.e., band 3, band 4, and band 5)


![Selection of the 1987 bands][logo20]


> Hold the Control key and select the three bands and click ok.

Choose your output filename as as 1987 Stack and click ok.

![Image of the 1987 Stack][logo21]

Repeat the same steps you did for step 7 for the 2002 Landsat image(i.e., band 3, band 4, and band 5)

![Selection of the 2002 bands][logo22]

Choose output filename as 2002 Stack and click ok.

![Image of 2002 Stack][logo23]


Go to file and add the niagara regional municipality boundaries to both views. Right click the shapefiles > zoom to layer and uncheck the municipal boundaries shapefile.

select the left view> click file> select open> go to the Change Detection Folder> in the Niagara open data fold choose municipal boundary (1) folder> select municipal boundary.shp > click open.



![Niagara municipal boundary shapefile 1][logo1]


![Niagara municipal boundary shapefile 1 on the visualization aera][logo35]


Right click on the municipal boundary.shp in the layer manager and select Zoom to layer Extent.


![Image of the Niagara municipal boundary shapefile 1][logo36]


Select the right view and repeat the above steps to add the municipal boundary shapefile. However, for thsi step you would choose municipal boundary (2) folder and select municipal boundary.shp and click opem. 


![Niagara municipal boundary shapefile 2][logo37]


![Niagara municipal boundary shapefile 1 on the visualization aera][logo38]


Right click on the municipal boundary.shp in the layer manager and select Zoom to layer Extent.


![Image of the Niagra municipal boundary shapefile 2][logo39]



**Subsetting  Stack Data from Region of Interest(ROI)**

Select the left view
Go to the search tool box and search my typing subset in the box> Double click Data from ROIs


 ![Subset Search][logo3]


Select Input File to Subset Via ROI dialogue box pops-up> For the select input file> Select 1987 Stack > Click ok.

![Subset Via ROI dialogue box][logo4]

Spatial Subset Via ROI parameters dialogue box pops-up> Select the municipal boundary.shp (i.e., the one at the bottom). 
Choose filename and Save as 1987 Subset> Click open > Cick ok.

![Subset Via ROI parameters dialogue box][logo5]

With the exception of 1987 Subset, uncheck all other layers in the left view in the layer manager.

![1987 Subset][logo6]

Repeat the same process of subsetting data for the 2002 Stack image in the right view.

Select the right view> for the select input file> Choose 2002 Stack and Click ok.

For the Spatial Subset Via ROI parameters  choose the municipal boundary.shp (i.e., the one at the top)
Choose 2002 Subset as the output file name> Click ok.

Also, with the exception of 2002 Subset, uncheck all other layers in the right view in the the layer manager.

![2002 Subset][logo7]


**Classification**

In this section we would like to use unsupervised classificaton(i.e., classification that allows the computer or software to classifying the land cover inro different land uses without any input of the user).

Click on the left view> Go to the tool box and expand the classification folder> expand unsupervised classification.
Double click K-means


![Classification folder in subset][logo8]


>Note:Unsupervised classification is where outcomes are based on the software analysis of an image without the user providing sample classes. The computer uses techniques to deteremine which pixels are related and groups them into classes.



Select 1987 Subset in the select input file of the classification input file dialogue box.


![Selection of 1987 Subset][logo9]


Click ok

K-means parameter dialogue box pop-up.Select number of classess as 3 > choose output filename as 1987 unsupervised > click ok.



![K-means parameter][logo10]



Result of the 1987 Unsupervised Classification


![image of 1987 unsupervised image][logo11]


Repeat the same classification process for 2002 Subset and name it as unsupervised 2002.

K-means parameter for 2002 unsupervised classification

![K-means parameter for 2002 Subset][logo12]


Result of the 2002 Unsupervised Classification


![image of 2002 unsupervised image][logo13]



Image showing  results of the 1987 and 2002 Unsupervised Classifications


![image of the two unsupervised image][logo14]



*Editing of class names and class colors*


Class Name|Class color|New Class Name|New Class Color
---|---|---|---
Class 1|Red|Waterbody|Blue
Class 2|Green|Human settlement|Yellow
Class 3|Blue|Bareland|Green


Go to the layer manager pane and Right click on the Classes[Below the K-Means (1987 subset)] on the left view and select edit class names and colors

Edit class names and colors dialogue box pop-up

![image of edit class names and colors dialogue box][logo15]


Move to class names> click on class1 and type the name Waterbody as the name in the edit box.
Having the above table as guide, repeat the same process for the other classes.

Move to class color> click on the class name and change the color by double clicking on the color beside the class name(use the above table as a guide).


Follow the same step to change the colors of the remaining classes using the table as a guide


![image of  edit classes and color for the 1987 unsupervised image][logo16]

Click ok when you are done with the editing



Repeat this step for the unsupervised 2002 image on the right view

Image showing resultof the editing process for the 1987 and 2002 Unsupervised Classifications.


![image result of the editing process for the two unsupervised classifications][logo17]



**Change Detection Analysis for the Entire Niagara Region**

Go to the tool box > expand the change detection folder

![Change Detection Folder][logo26]

Double click change detection statistics

Select unsupervised 1987(i.e.' K-means 1987 Subset) as the 'initial state' image and click ok.


![Selection of initial state][logo27]


Select unsupervised 2002(i.e., K-means 2002 Subset) as the 'final stage' image and click ok.


![Selection of final state][logo28]


Definine Equivalent parameter dialogue box pops-up> select unclassified for both the initial state classess and the final state classes> click ok.


![Define Equivalent parameter][logo29]


Change Detection Statistics Output dialogue box pops-up> Choose your output filename and save as Change Detection Statistics> click ok.


![Change detection statistics output dialogue box][logo30]


Change Detection Statistics results pop-up. you can see the percentage change, pixel change and area change (in square metre). you can also save your result as a text file. click file and save.

Pixel Change result

![Change Detection pixel result][logo32]


Percentage Change result


![Change Detection percentage result][logo33]


Area Change result


![Change Detection Area result][logo34]





**Change Detection Analysis for St. Catharines**

Close the previous Change Detection Statistics results

Click on the left view> go to file > add the St. Catharines boundary shapefile


![St. Catharines Shapefile][logo43]


Click of the right view and repeat the same process

Data manager dialogue box pops-up> select Municipal Structure and click load


![Data Manager dialogue box][logo44]



Close the Data manager dialogue box (x)


**Generating the Study Area for St. Catharines**

Click on the left view and generate a subset for St. Catharines by following the same procedure you used to subset Niagara boundary shapefile from the stacked images.

For the select input choose 1987 Unsupervised> for the input ROIs choose the Scheduled Municipal Structure shp.> and save as 1987 St. Catharines

Now uncheck the Scheduled Municipal Structure shp. and the 1987 Unsupervised image> right click the 1987 St. Catharines and select Zoom to Layer Extent.



Repeat the same procedure for the right view (i.e. for the 2002 image)

For the select input choose 2002 Unsupervised> for the input ROIs choose the Scheduled Municipal Structure shp.> and save as 2002 St. Catharines

Now uncheck the Scheduled Municipal Structure shp. and the 2002 Unsupervised image> right click the 1987 St. Catharines image and select Zoom to Layer Extent.


![Result of the Subset for both images][logo45]




![Zoom Result of the Subset for both images][logo46]



**Performing Change Detection Statistic**

Repeat Niagara's Change Detection Statistics procedures for that of St. Catharines

Select 1987 St. Catharines as the 'initial state' image and click ok.


Select 2002 St. Catharines as the 'final stage' image and click ok.


Define Equivalent parameter dialogue box pops-up> select unclassified for both the initial state classess and the final state classes> click ok.


Change Detection Statistics Output dialogue box pops-up> Choose your output filename and save as St. Catharines Change Detection Statistics> click ok.




The St. Catharines Change Detection Statistics results pop-up. you can see the percentage change, pixel change and area change (in square metre). you can also save your result as a text file. click file and save.

Pixel Change result

![St. Catharines Change Detection pixel result][logo40]


Percentage Change result


![St. Catharines Change Detection percentage result][logo41]


Area Change result


![St. Catharines Change Detection Area result][logo42]
 
 
 
 
 
### Conclusion

Content

### Etc.
 
 
 









<!--- Please use reference style images so that it is easier to update pictures later --->

[dsllogo]: dsl_logo.png
[logo1]: logo1.PNG
[logo2]: logo2.PNG
[logo3]: logo3.PNG
[logo4]: logo4.PNG
[logo5]: logo5.PNG
[logo6]: logo6.PNG
[logo7]: logo7.PNG
[logo8]: logo8.PNG
[logo9]: logo9.PNG
[logo10]: logo10.PNG
[logo11]: logo11.PNG
[logo12]: logo12.PNG
[logo13]: logo13.PNG
[logo14]: logo14.PNG
[logo15]: logo15.PNG
[logo16]: logo16.PNG
[logo17]: logo17.PNG
[logo18]: logo18.PNG
[logo19]: logo19.PNG
[logo20]: logo20.PNG
[logo21]: logo21.PNG
[logo22]: logo22.PNG
[logo23]: logo23.PNG
[logo24]: logo24.PNG
[logo25]: logo25.PNG
[logo26]: logo26.PNG
[logo27]: logo27.PNG
[logo28]: logo28.PNG
[logo29]: logo29.PNG
[logo30]: logo30.PNG
[logo31]: logo31.PNG
[logo32]: logo32.PNG
[logo33]: logo33.PNG
[logo34]: logo34.PNG
[logo35]: logo35.PNG
[logo36]: logo36.PNG
[logo37]: logo37.PNG
[logo38]: logo38.PNG
[logo39]: logo39.PNG
[logo40]: logo40.PNG
[logo41]: logo41.PNG
[logo42]: logo42.PNG
[logo43]: logo43.PNG
[logo44]: logo44.PNG
[logo45]: logo45.PNG
[logo46]: logo46.PNG
[logo47]: logo47.PNG
