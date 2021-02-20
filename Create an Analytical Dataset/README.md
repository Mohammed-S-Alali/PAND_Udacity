# The Business Problem
Pawdacity is a leading pet store chain in Wyoming with 13 stores throughout the state. This year, Pawdacity would like to expand and open a 14th store. Your manager has asked you to perform an analysis to recommend the city for Pawdacity’s newest store, based on predicted yearly sales.

Your first step in predicting yearly sales is to first format and blend together data from different datasets and deal with outliers.

Your manager has given you the following information to work with:

1. The monthly sales data for all of the Pawdacity stores for the year 2010.
2. NAICS data on the most current sales of all competitor stores where total sales is equal to 12 months of sales.
3. A partially parsed data file that can be used for population numbers.
4. Demographic data (Households with individuals under 18, Land Area, Population Density, and Total Families) for each city and county in the state of Wyoming. For people who are unfamiliar with the US city system, a state contains counties and counties contains one or more cities.

<center><b>Map of Wyoming Counties</b></center>

![](https://video.udacity-data.com/topher/2019/August/5d47a493_wyoming-county-map/wyoming-county-map.gif)


# Steps to Success
## Step 1: Business and Data Understanding
Your project should include a description of the key business decisions that need to be made.

## Step 2: Building the Training Set
To properly build the model, and select predictor variables, create a dataset with the following columns:

`City`
`2010 Census Population`
`Total Pawdacity Sales`
`Households with Under 18`
`Land Area`
`Population Density`
`Total Families`

This dataset will be your training set to help you build a regression model in order to predict sales in the Practice Project in the next lesson. Every row should have sales data because we're trying to predict sales.

<b>Notes</b>
You should be consolidating the data at the city level and <b>not at the store level.</b> We only have data at the city wide level so any analysis at the store level will not be sufficient to complete this analysis.

We simply need to focus on cleaning up and blending the data together in this step.

If you’ve done everything correctly, the sum for each of the above columns should be:

- <b>Census Population:</b> 213,862
- <b>Total Pawdacity Sales:</b> 3,773,304
- <b>Households with Under 18:</b> 34,064
- <b>Land Area:</b> 33,071
- <b>Population Density:</b> 63
- <b>Total Families:</b> 62,653
with <b>11 rows of data</b>

For Alteryx users:

Use the Autofield Tool to help quickly convert your data fields into the appropriate datafields for analysis.

Research these <a href = "http://help.alteryx.com/10.6/index.htm#Reference/Functions.htm#String">three specific formulas</a> to help you get rid of unwanted characters in the Formula tool: ReplaceFirst, Left, FindString

## Step 3: Dealing with Outliers
Once you have created the dataset, look for outliers and figure out how deal with your outliers. Use the IQR method to determine if there are outlier cities for each of the variables and then justify which city that has at least one outlier value should be removed.

<b>IQR Steps</b>

To calculate the upper fence and the lower fence, here are the exact steps:

1. Calculate 1st quartile Q1 and 3rd quartile Q3 of the dataset. You can use the Excel function QUARTILE.INC or QUARTILE.EXC

2. Calculate the Interquartile Range: IQR = Q3 - Q1

3. Add 1.5 IQR to Q3 to get the upper fence: Upper Fence = Q3 + 1.5 IQR

4. Subtract 1.5 IQR to Q1 to get the lower fence: Lower Fence = Q1 - 1.5 IQR

5. Values above the Upper Fence and values below the Lower Fence are outliers
