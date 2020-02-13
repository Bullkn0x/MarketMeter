
# [TDQA](#Test) tool  
TDQA leverages fundamental probability theory and statistical techniques to measure the separation, (dis)similarity, of tag level distributions within a given experimental condition and/or between exprimental conditions. 


#Reported Metrics
A detailed description of the mathematical theory behind the computated metrics below can be found here. 
However, here is a quick overview of what is computed and reported: 

### ***Jensen-Shannon Distance (JS)***:

The JS is a metric that quantifies the difference, or statistical distance between two statistical objects, e.g. probability distributions; thereby providing a way to assess the "closeness" between two probability density functions (pdfs).


### ***Dissimilarity Index (DSI)***: 

The DSI of a given experimental condition is a measure of the **overall** separation or disimilarity between the four tag pdfs. 

### ***Shannon Entropy (H)***

The H is calculated for each of the four tag pdfs as a measure of the amount of "information" or "uncertainty" of the data given from the source. 


## Access and Dependencies for TDQA



**4**. Apply TDQA tool by invoking the plotter, plot-aggregates, with the use of certain flags (as described in the next section). 

## Flags for TDQA Use Cases
Depending on the user's motivations, TDQA may be invoked by either of **two available command-line flags**:

### Option 1:  --tag_diagnostic

### Option 2:  --tag_compare



## Inputs
As described in "Access and Dependencies for TDQA" above, user must 



## Outputs 


###  --tag_diagnostic 


<tr>
<td> <img src="https://images.sftcdn.net/images/t_app-cover-l,f_auto/p/ce2ece60-9b32-11e6-95ab-00163ed833e7/260663710/the-test-fun-for-friends-screenshot.jpg", alt="Drawing" width="250"/> </td>
<td> <img src="Images/Intra_Cycle_Analysis_sgPETE_QC_Heatmap.png" alt="Drawing" style="width: 400px;"/> </td>
</tr>


### [Figure 1a.](http://ghe-rss.roche.com/rsc/TAG/blob/master/TDQA/Images/Intra_Cycle_Analysis_Rocket_Heatmap.png)
**Condition1_1D_2D_contour_hist.png**

In Figure 1a. on the left, two subplots are displayed showing the four tag level signals distributed in 1D (top) and 2D, as versus dwell time (bottom). The 1D illustration displays each tag level signal distributed as a simple ***histogram*** with a ***bin length of 0.02 from range of -0.5 to 1.5***. The 2D illustration displays each tag level signal, x-axis, versus their respective dwell time signal, y-axis, fitted using a ***kernel density estimation using Gaussian kernels***. 


# [TDQA tool](#test)  (http://ghe-rss.roche.com/rsc/TAG/blob/master/TDQA/Images/Intra_Cycle_Analysis_Rocket_Heatmap.png)
**Intra_Cycle_Analysis_Condition1_Heatmap.png**

In Figure 1b. on the right, four subplots are shown, one for each tag and their corresponding cycle by cycle comparisons for computed Jensen Shannon distances. In this way, ***all possible cycle pair combinations*** within *one experimental condition* are assessed, each quadrant illustrating the JS values for the respective tag, along with their corresponding color representation of the relative intensities captured in the heatmap. As can be seen in the legend, the higher the red intensity, the greater the value for the JS value and therefore the greater the statistical distance measured between the pairs.  

### --tag_compare

*Usage:*(#test)
>```
>plot aggregates -q 'condition in ["Condition_1", "Condition_2"]' --tag_compare
>```
>
*Outputs*:
>```
>YYMMDD_Exeriment_Name/aggregated_results/tag_compare_plots
>
>Condition1_Condition2_hist_levels.png
>Condition1_Condition2_2D_kde_contour.png
>Tag_Between_Pairs_Condition1_Condition2_hist.png
>Intra_Cycle_Analysis_Condition1_Heatmap.png
>Intra_Cycle_Analysis_Condition2_Heatmap.png
>```

<tr>
<td> <img src="Images/Rocket_sgPETE_QC_hist_levels.png" alt="Drawing" style="width: 800px;"/> </td>
<td> <img src="Images/Rocket_sgPETE_QC_2D_kde_contour.png" alt="Drawing" style="width: 500px;"/> </td>
</tr>


<td> <img src="Images/Tag_Between_Paris_Rocket_sgPETE_QC_hist.png" alt="Drawing" style="width: 500px;"/> </td>
<td> <img src="Images/Intra_Cycle_Analysis_Rocket_Heatmap.png" alt="Drawing" style="width: 500px;"/> </td>
<td> <img src="Images/Intra_Cycle_Analysis_sgPETE_QC_Heatmap.png" alt="Drawing" style="width: 500px;"/> </td>

### [Figure 2a.](http://ghe-rss.roche.com/rsc/TAG/blob/master/TDQA/Images/Intra_Cycle_Analysis_Rocket_Heatmap.png)
**Condition1_Condition2_hist_levels.png**

In Figure 2a. on the top left, while sharing their x-axis, two subplots display the tag level distributions for the pair of conditions being compared. The tag level distributions are displayed as a ***histogram*** with a ***bin length of 0.02 from range of -0.5 to 1.5***. 


### [Figure 2b.](http://ghe-rss.roche.com/rsc/TAG/blob/master/TDQA/Images/Intra_Cycle_Analysis_Rocket_Heatmap.png)
**Condition1_Condition2_2D_kde_contour.png**

In Figure 2b. on the top right, while sharing their x-axis, two subplots display the tag versus dwell level distributions for the pair of conditions being compared. The 2D illustrations display each tag level signal, x-axis, versus their respective dwell time signal, y-axis, fitted using a ***kernel density estimation using Gaussian kernels***. 



### [Figure 2c.](http://ghe-rss.roche.com/rsc/TAG/blob/master/TDQA/Images/Intra_Cycle_Analysis_Rocket_Heatmap.png) 
**Tag_Between_Pairs_Condition1_Condition2_hist.png**

In Figure 2c. on the bottom left, a bar plot is shown, illustrating, in tag order, the JS distance values measured between pair of conditions, as well as within each respective condition. JS distance values are obtained within a condition by measuring the *JS distance* ***between every possible split subsetting*** and reporting the **mean** (bar) and the **standard error** as displayed as an error bar.

### [Figure 2d.](http://ghe-rss.roche.com/rsc/TAG/blob/master/TDQA/Images/Intra_Cycle_Analysis_Rocket_Heatmap.png) 
**Intra_Cycle_Analysis_Condition1_Heatmap.png**

In Figure 2d. on the bottom middle, the heatmap for Condition 1 is displayed. Refer to Figure 1b. for details.


### [Figure 2e.](http://ghe-rss.roche.com/rsc/TAG/blob/master/TDQA/Images/Intra_Cycle_Analysis_Rocket_Heatmap.png)  
**Intra_Cycle_Analysis_Condition2_Heatmap.png**

In Figure 2e. on the bottom right, the heatmap for Condition 2 is displayed. Refer to Figure 1b. for details.


This command initiates a side by side comparison of the chosen pair of conditions. Five plots are generated for a comparison and stored in a folder called **tag_compare_plots** within the **aggregated_results** directory as shown below:






```python

```
