# rice-btcmp-hw5-matplotlib-challenge
Using Matplotlib library to analyze results of a cancer drug study

## Project objective

As a senior data analyst at the company, you've been given access to the complete data from their most recent animal study. In this study, 249 mice identified with SCC tumor growth were treated through a variety of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals' drug of interest, Capomulin, versus the other treatment regimens. You have been tasked by the executive team to generate all of the tables and figures needed for the technical report of the study. The executive team also has asked for a top-level summary of the study results.

## Instructions

- Before beginning the analysis, check the data for any mouse ID with duplicate time points and remove any data associated with that mouse ID.

- Use the cleaned data for the remaining steps.

- Generate a summary statistics table consisting of the mean, median, variance, standard deviation, and SEM of the tumor volume for each drug regimen.

- Generate a bar plot using both Pandas's `DataFrame.plot()` and Matplotlib's `pyplot` that shows the number of total mice for each treatment regimen throughout the course of the study.

  - **NOTE:** These plots should look identical.

- Generate a pie plot using both Pandas's `DataFrame.plot()` and Matplotlib's `pyplot` that shows the distribution of female or male mice in the study.

  - **NOTE:** These plots should look identical.

- Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Calculate the quartiles and IQR and quantitatively determine if there are any potential outliers across all four treatment regimens.

- Using Matplotlib, generate a box and whisker plot of the final tumor volume for all four treatment regimens and highlight any potential outliers in the plot by changing their color and style.

  **Hint**: All four box plots should be within the same figure. Use this [Matplotlib documentation page](https://matplotlib.org/gallery/pyplots/boxplot_demo_pyplot.html#sphx-glr-gallery-pyplots-boxplot-demo-pyplot-py) for help with changing the style of the outliers.

- Select a mouse that was treated with Capomulin and generate a line plot of tumor volume vs. time point for that mouse.

- Generate a scatter plot of mouse weight versus average tumor volume for the Capomulin treatment regimen.

- Calculate the correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin treatment. Plot the linear regression model on top of the previous scatter plot.

- Look across all previously generated figures and tables and write at least three observations or inferences that can be made from the data. Include these observations at the top of notebook.

And as a final considerations - proper labeling of the plots has to be used, including properties such as: plot titles, axis labels, legend labels, *x*-axis and *y*-axis limits, etc.

### Input data:

Input data consists of two *.csv files containing related data for the study:

* [Mouse_metadata.csv](data/Mouse_metadata.csv) with the following information and data types:<br>
  <img src="figures\mouse_metadata.PNG" style="zoom:100%;" align="center"/><br>with the following data:
  * `Mouse ID`	column contains individual IDs for each mouse (data type - string)	
  * `Drug Regimen`	column contains names of the drugs tested (data type - string)
  * `Sex`	column contains mice gender (data type - string)	
  * `Age_months`	column contains mice age (data type - integer)
  * `Weight (g)`	column contains mice weight in grams (data type - float)
* [Study_results.csv](data/Study_results.csv) with the following information and data types:<br>
  <img src="figures\study_results.PNG" style="zoom:100%;" align="center"/><br>with the following data:
  * `Mouse ID`	column contains individual IDs for each mouse (data type - string)	
  * `Timepoint`	column contains time reference for the measurements being taken  (data type - integer)
  * `Tumor Volume (mm3)`	column contains recorded tumor volumes (data type - float)	
  * `Metastatic Sites`	column contains metastatic site count (data type - integer)

### Observations:

1. A total of 10 drugs were tested on 249 mice with an almost equal split in gender as shown in the below pie chart:<br>
   <img src="figures\mice_gender_pie.png" style="zoom:100%;" align="center"/>
2. Among the four top drugs tested, only Infubinol was shown to contain outliers (one), as shown in the figure below.<br>
   <img src="figures\drug_vs_vol_boxplot.png" style="zoom:100%;" align="center"/>
   <br>Here, we can see that Infubinol & Ceftamin consistently outperform the Capamulin & Remicane.
3. As we have been asked to review performance of Capomulin drug in particular, a positive trend in the reduction of tumor volume with time could be clearly observed using the Mouse ID r554 test results:<br>
   <img src="figures\timepoint_vs_vol_for_mouse_id_r554.png" style="zoom:100%;" align="center"/>
4. Average tumor volume shows strong positive correlation with mice weight, with correlation coefficient ~ 0.93<br>
   <img src="figures\weight_vs_vol_scatter_w_fit.png" style="zoom:100%;" align="center"/>

