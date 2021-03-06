![DSL Logo][dsllogo]        ![image of the two unsupervised image][logo14]


#  Niagara's Land Cover Change Analysis: An Introduction to Change Detection Analysis

### Introduction

For this project, I will explore Landsat images using ENVI 5.5.3 to identify changes in land cover between 1987 and 2002 within the Niagara Region. Land Cover will be classified into three groups, namely: Water bodies, Bare lands, and Human Settlement. Data for this project were gathered from the United States Geological Survey (USGS) EarthExplorer and the Niagara Open data websites. Data retrieved from the USGS EarthExplorer website were Landsat 5 and Landsat EMT7 images for the years 1987 and 2002, respectively. The Niagara Open Data website, provided my study with boundary shapefiles for the Niagara Region and St. Catharines. I collected the boundary shapefile for St. Catharines because I had wanted to understand changes in land cover at the individual municipal level, in addition to that of the entire region.
Furthermore, since I am staff at Brock University which is also located in St. Catharines, thus findings of land cover change in St. Catharines will be of benefit to environmental researchers at Brock University, environmental activists, authorities at the St. Catharines' Municipality and in particular the Niagara Region Municipality at a larger scale. The main purpose of this project is to introduce first time users - particularly students - to some Remote Sensing techniques. Some of these techniques include **Layer Stacking, Subsetting Region of Interest, Classification, and Change Detection Statistics**.




### Procedures

**STEP ONE : Adding of Data**

Download the **Change Detection Compressed Folder** from the **GitHub Link** below:
https://github.com/BrockDSL/Change_Detection_Analysis_Remote_Sensing

Locate the downloaded file on your computer. Right-click the file and extract it to a location where you can easily find it, such as your Documents folder.

Open **Envi 5.5.3** Software.


 ![Envi 5.5.3 Visualization view][logo31]



Click the '**View** button on the **Menu Bar** and select **Two Vertical Views**. 

Altenately hold **Alt + 2**.


 ![Two Vertical Views][logo2]



>NB: This operation will generates a **Left View** and a **Right View** on the visualization area. 


Click on the **Left View** > Go to **File** > Go to the location of the downloaded **Remote Sensing** Data > Select **Band 3, Band 4, and Band 5** of your **1987 Landsat** data > Click **Open**.


![Loading of 1987 bands][logo24]




Alternately you can hold **Ctrl + O**.

Also select the **Right View** and repeat the same process you added the 1987 landsat data. Select **Band 3, Band 4, and Band 5** of your **2002 Landsat Data** and click **Open**.


![Loading of 2002 bands][logo25]





**STEP TWO : Layer Stacking (Joining of bands)**

For this step I will like to join the three bands of each view to get a single image for each view.

Click on the **Left View** > at the top right corner of your visualization view, you will see **Tool Box** > Below the **Tool Box** expand the **Raster Management** folder and double-click **Build Layer Stack**.


![Raster management folder showing layer stack][logo18]




**Layer Stacking Parameters** dialogue box pops up.


![Layer Stack Dialogue box][logo19]




Click on the **three dot in the box** at the right side of the **Input Raster Box** > Select all the **1987 Bands** in the **Select Input File** (i.e., **Band 3, Band 4, and Band 5**).


![Selection of the 1987 bands][logo20]




>Hold the Control key and select the three bands and click **Ok**.

Choose your **Output Filename** as **1987 Stack** and Click **Ok**.


![Image of the 1987 Stack][logo21]



Repeat the same layer stacking procedures you use for the 1987 landat image and generate a stacked image for the **2002 Landsat** image (i.e., **Band 3, Band 4, and Band 5**).


![Selection of the 2002 bands][logo22]




Choose **Output Filename** as **2002 Stack** and click **Ok*.


![Image of 2002 Stack][logo23]




**STEP THREE : Adding of Niagara Regional Boundary Shapefiles**

Go to **File** and add the **Niagara Regional Municipality Boundary Shapefiles** to both **Views**. Below are the recommended procedures in adding the shapefiles to your images:


Select the **Left View** > Click **File** > Select **Open** > Go to the **Change Detection** Folder > In the **Niagara Open Data** folder choose **Municipal Boundary (1)** folder > Select **Municipal Boundary.shp** > Click **Open**.



![Niagara municipal boundary shapefile 1][logo1]



![Niagara municipal boundary shapefile 1 on the visualization aera][logo35]




Right click on the **Municipal Boundary.shp** in the **Layer Manager** and select **Zoom to layer Extent**.


![Image of the Niagara municipal boundary shapefile 1][logo36]




Select the **Right View** and repeat the above procedures to add the **Municipal Boundary Shapefile**. However, for this step you would choose **Municipal Boundary (2)** folder and select **Municipal Boundary.shp** and click **Open**. 


![Niagara municipal boundary shapefile 2][logo37]




![Niagara municipal boundary shapefile 1 on the visualization aera][logo38]




Right click on the **Municipal Boundary.shp** in the **Layer Manager** and select **Zoom to layer Extent**.


![Image of the Niagra municipal boundary shapefile 2][logo39]






**STEP FOUR : Subsetting  Stack Data from Region of Interest(ROI)**

Select the **Left View**.

Go to the **Search Tool Box** and search by typing **Subset** in the search box > Double-click **Data from ROIs**.


 ![Subset Search][logo3]




**Select Input File to Subset Via ROI** dialogue box pops up > For the **Select Input File**, choose **1987 Stack** > Click **Ok**.


![Subset Via ROI dialogue box][logo4]




**Spatial Subset Via ROI Parameters** dialogue box pops up > Select the **Municipal Boundary.shp** (i.e., *the one at the bottom*). 

Choose **Output Filename** and save as **1987 Subset** > Click **Open** > Click **Ok**.


![Subset Via ROI parameters dialogue box][logo5]




With the exception of **1987 Subset**, **uncheck** all other layers in the **Left View** in the **Layer Manager**.


![1987 Subset][logo6]





Repeat the same process you used for subsetting the 1978 data for the **2002 Stack** image in the **Right View**.

Select the **Right View** > For the **Select Input File**, choose **2002 Stack** and Click **Ok**.

For the **Spatial Subset Via ROI parameters**,  choose the **Municipal Boundary.shp** (i.e., *the one at the top*)

Choose **2002 Subset** as your **Output Filename** > Click **Ok**.

Also, with the exception of 2002 **Subset**, **uncheck** all other layers in the **Right View** in the **Layer Manager**.


![2002 Subset][logo7]





**STEP FIVE : Classification**

In this section I will like to use unsupervised classificaton(i.e., classification that allows the computer or software to classify the land cover into different land uses without any input of the user).

Click on the **Left View** > Go to the **Tool Box** and Expand the **Classification** folder> Expand **Unsupervised Classification** >
Double-click **K-means**.


![Classification folder in subset][logo8]




>Note:Unsupervised classification is when outcomes are based on the software analysis of an image without the user providing sample classes. The computer uses techniques to deteremine which pixels are related and groups them into classes.



Select **1987 Subset** as the **Select Input File** from the **Classification Input File** dialogue box.


![Selection of 1987 Subset][logo9]




Click **Ok**.

**K-means Parameter** dialogue box pops up. Select **number of classes** as **3** > Choose **Output Filename** as **1987 Unsupervised** > Click **Ok**.



![K-means parameter][logo10]




>Result of the 1987 Unsupervised Classification


![image of 1987 unsupervised image][logo11]



Repeat the same classification process for your **2002 Subset** and name it as **Unsupervised 2002**.

K-means parameter for 2002 unsupervised classification


![K-means parameter for 2002 Subset][logo12]





Result of the 2002 Unsupervised Classification.


![image of 2002 unsupervised image][logo13]





Image showing  results of the 1987 and 2002 Unsupervised Classifications.


![image of the two unsupervised image][logo14]






**STEP SIX : Editing of Class Names and Class Colors**


Class Name| Class Color| New Class Name| New Class Color
---| ---| ---| ---
Class 1| Red| Waterbody| Blue
Class 2| Green| Human settlement| Yellow
Class 3| Blue| Bareland| Green



Go to the **Layer Manager** pane and Right click on **Classes**[Below the K-Means (1987 subset)] on the **Left View** and select **Edit Class Names and Colors**.

**Edit Class Names and Colors** dialogue box pops up.


![image of edit class names and colors dialogue box][logo15]





Move to **Class Names**> click on **Class 1** and type the name Waterbody as the name in the edit box.
Use the table above as guide, repeat the same process for the other classes.

Move to **Class Color** > Click on the **Class Name** and change the **Color** by **double-clicking** on the **Color** beside the **Class Name** (*use the table above as a guide*).

Follow the same procedure to change the colors of the remaining classes using the table as a guide.


![image of  edit classes and color for the 1987 unsupervised image][logo16]




Click **Ok** when you are done with the editing.


Repeat these procedures for the **Unsupervised 2002** image on the **Right View**.

<The Image below shows result of the editing process for the 1987 and 2002 Unsupervised Classifications.


![image result of the editing process for the two unsupervised classifications][logo17]





**STEP SEVEN : Change Detection Analysis for the Entire Niagara Region**

Go to the **Tool Box** > Expand the **Change Detection** folder.


![Change Detection Folder][logo26]




Double-click **Change Detection Statistics**.

Select **Unsupervised 1987** (i.e. *K-means 1987 Subset*) as the **Initial state** image and click **Ok**.


![Selection of initial state][logo27]




Select **Unsupervised 2002** (i.e., *K-means 2002 Subset*) as the **Final Stage** image and click **Ok**.


![Selection of final state][logo28]




**Definine Equivalent Parameter** dialogue box pops up > Select **unclassified** for both **Initial State Classes** and **Final State Classes** > Click **Ok**.


![Define Equivalent parameter][logo29]




**Change Detection Statistics Output** dialogue box pops up> Choose your **Output Filename** and save as **Change Detection Statistics**> Click **Ok**.


![Change detection statistics output dialogue box][logo30]





**Change Detection Statistics** results pop up. You can view the **percentage change, pixel count change and area change (in square metre)** for the three types of Land Cover. You can also save your result as a **Text File**. Click **File** and **Save**.


**Pixel Count Change Result**


![Change Detection pixel result][logo32]





The change detection statistics result for the pixel count revealed that there were significant decreases in water bodies (i.e., **-76549**) and bare lands (i.e., **-146477**) whereas human settlement (i.e., **+223026**) experienced an increase in Niagara from 1987 to 2002. 



**Percentage Change Result**


![Change Detection percentage result][logo33]




The change detection statistics result in terms of percentage change showed that water bodies (i.e., **-10.09%**)  and bare lands (i.e., **-12.92%**) experienced losses in land cover. In contrast, Human Settlement (i.e., **+12.69%**) experienced an increase in Niagara from 1987 to 2002. 




**Area Change Result**


![Change Detection Area result][logo34]




With regards to area (i.e., in Square meters), results from the change detection statistics  revealed  decreases in waterbodies (i.e., **-68,894,100**) and bare lands (i.e., **-131,829,300**), whereas human settlement (i.e., **+200,723,400**) experienced an increase in Niagara from 1987 to 2002. 





**STEP EIGHT : St. Catharines' Change Detection Analysis**

Close the previous **Change Detection Statistics results**.

Click on the **Left View** > Go to **File** > Add the **St. Catharines Boundary Shapefile**.


![St. Catharines Shapefile][logo43]





Click of the **Right View** and repeat the same process.

**Data Manager** dialogue box pops up > Select **Scheduled Municipal Structure shp.** and click **Load**.


![Data Manager dialogue box][logo44]





Close the **Data Manager** dialogue box **(x)**.




**Generating the Study Area for St. Catharines**

Click on the **Left View** and generate a **subset** for **St. Catharines** by following the same procedure you used to **subset** the **Niagara boundary shapefile** from the **stacked images**.

For the **Select Input**, choose **1987 Unsupervised**> For the **Input ROIs**, choose the **Scheduled Municipal Structure shp.**> and save as **1987 St. Catharines**.

Now **uncheck** the **Scheduled Municipal Structure shp.** and the **1987 Unsupervised** image> Right click the **1987 St. Catharines** image and select **Zoom to Layer Extent**.



Repeat the same procedure for the right view (i.e. *for the 2002 image*)

For the **Select Input**, choose **2002 Unsupervised**> For the **Input ROIs**, choose the **Scheduled Municipal Structure shp.** > and save as **2002 St. Catharines**.

Now **uncheck** the **Scheduled Municipal Structure shp.** and the **2002 Unsupervised** image> Right click the **1987 St. Catharines** image and select **Zoom to Layer Extent**.


![Result of the Subset for both images][logo45]





<The figure above shows images of St. Catharines that have be generated from unsupervised images. 



![Zoom Result of the Subset for both images][logo46]





<The figure above shows images of the zoomed results of the subsetted images. 




**Performing Change Detection Statistic**

Follow Niagara's Change Detection Statistics procedures  in order to generate a change detection result for St. Catharines.

Select **1987 St. Catharines** as the **Initial State** image and click **Ok**.


Select **2002 St. Catharines** as the **Final Stage** image and click **Ok**.


**Define Equivalent Parameter** dialogue box pops up> Select **unclassified** for both **Initial State Classes** and **Final State Classes**> Click **Ok**.


**Change Detection Statistics Output** dialogue box pops up> Choose your **Output Filename** and save as **St. Catharines Change Detection Statistics**> Click **Ok**.



The St. Catharines **Change Detection Statistics** results pop-up. You can  now see changes in land cover in terms of **percentage, pixel count and area (in square metre)**. You can also **Save** your result as a text file. 

Click **File** on top of the pop-up Change Destection Result and select **Save**.



**Pixel Count Change Result**


![St. Catharines Change Detection pixel result][logo40]





The change detection statistics result for the pixel count revealed that there were slight decreases in water bodies (i.e., **-2072**) and bare lands (i.e., **-1306**) whereas human settlement (i.e., **+3378**) also experience a slight increase in St. Catharines from 1987 to 2002. 



**Percentage Change Result**


![St. Catharines Change Detection percentage result][logo41]





The change detection statistics result in terms of percentage change showed that water bodies (i.e., **-4.73%**) and bare lands (i.e., **-2.83%**) experienced slight losses. In contrast, human settlement (i.e., **+3.24%**) experienced a slight increase from 1987 to 2002. 




**Area Change Result**


![St. Catharines Change Detection Area result][logo42]
 
 
 
 
 
 With regards to  the area (i.e., in Square meters), results from the change detection statistics  revealed  decreases in water bodies (i.e., **-1,864,800**) and bare lands (i.e., **-3,040,200**), whereas human Settlement (i.e., **+1,175,400**) experience an increase from 1987 to 2002. 




### Conclusion
This project used a combination of change detection analysis and other techniques (i.e., layer stacking, subsetting region of interest, and classification)  to identify changes in land cover in the Niagara Region from 1987 to 2002. Also, I  used these techniques to examine changes in land cover at the individual municipal level, particularly in the St. Catharines Municipality. I found out that changes in areas covered by human settlement were negatively associated with changes in areas covered by water bodies and bare lands within these 15 years. This result implied that an increase in human settlement led to a decrease in water bodies and bare lands in St. Catharines and entire Niagara regional municipality.

For my future research, I would like to re-run my analysis using dissemination areas or other units smaller than the entire municipality and St. Catharines to see if these patterns also hold. This project identified the extent of land cover change in the Niagara Region and proposed recommendations for future action. The municipal level analysis substantiated the existence of land cover change within the region and recognized considerable factors contributing to changes in land cover from 1987 to 2002. The project findings are supported by descriptive statistical analysis and serve as a beginning to further analysis of land cover change in the Niagara Region.




 
 
 




**Author**: Philip Dwomoh

**Position**: Map, Data and GIS Library Student Assistant

**Organization**: Brock University Digital Scholarship Lab 








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
