# DS-5500-HW 2

## Solution 4:


Here, we're investigating the relationship between GDP Per Capita and Life Expectancy. For the experiment, I'll consider GDP per capita as X and Life Expectancy as Y because my assumption is as Income increases, people can afford better health care and get a better standard of living overall which might result into average Life Expectancy of a person. I also believe that this relationship cannot be perfectly linear as there will be an upper limit in age and as the Life expectancy increases, the rate of increase after one point will be slow as it reaches that upper limit of age.

![Relationship between GDP Per Capita and Life Expectancy](figures/Fig1.png)
###### Figure 1: Scatter Plot for GDP per Capita and Life Expectancy

As observed from the plot below, In the raw data for all countries, the data is densly populated and the relationship is not linear and hence this confirms one of the assumption which could be a possible explaination behind this. Now to proceed further, the data would require a transformation. Given the nature of the graph, the first choice would be log tranformation  

![Relationship between log transformed GDP Per Capita and Life Expectancy](figures/Fig2.png)
###### Figure 2: Scatter Plot for Log tramnsformed GDP per Capita and Life Expectancy
The plot now shows a better relationship between both variables which would be more useful in identifying a relationship between them and now we can try our first model.

<img src="https://github.com/rathiromil13/DS-5500-HW-2/blob/master/figures/Fig3.png" width="400" height ="600">

###### Figure 3: Statistics for First Model

Using X ~ Log (GDP per Capita) and Y ~ Life Expectancy in Years,for the data the adjusted R-squared value obtained is 0.616 which is mainly due to the fact that data is stil not completely good for regression. The reasons behind that is it doesn't capture enough variables as predictor, and the data wrangling can be performed more efficiently as here we've data corresponding to each country and continent for each year, thus data doesn't capture a strong relationship to build on.

![Fit for First Model](/figures/Reg1.png)
###### Figure 4: Fit for First Model on Data

For the former reason, I added the variable of time to the model. Time is an important factor here as over the time as GDP per capita as well as Life Expectancy both have shown monotonically increasing trend. The possible reason could be as GDP per capita increases with time, people can invest more in healthcare and get better services overall. The sanitary conditions also improve which explains that one of the other assumption might also be true. 
Here are the results for Linear Regression with Multiple Variable

<img src="https://github.com/rathiromil13/DS-5500-HW-2/blob/master/figures/time.png" width="400" height ="600">

###### Figure 5: Summary for First Model with Time as another variable.

The adjusted R squared has improved to ~0.70 with inclusion of time.

To add more layer of data wrangling, I tried to get the mean of gdp per capita and life expectancy across all countries for a given year. The distribution looks as follows:

![Mean GPD per capita and Mean Life Expectancy for each year](figures/Mean_Life_GDP.png)
###### Figure 5: Scatter Plot for Mean GDP per capita and Mean Life Expectancy
It looks good and shows almost linear relationship between the two variables, thus next step would be to model them directly for the transformed dataset.

<img src="https://github.com/rathiromil13/DS-5500-HW-2/blob/master/figures/mean1.png" width="400" height ="600">

###### Figure 6: Statistics for model with Mean GDP per capita and Mean Life Expectancy

Here, the adjusted R-squared is very high (~0.955), upon further inspection we can observe that coefficient of GDP per capita is very low (~0.0016) which reduces it's effect to almost nil. Thus we need to try another transformation to get a better model.

Now, on exploring the relationship between Life Expectancy and log of GDP per capita, we can see coefficient is positive which is expected out of it and Adjusted R squared is still high of (~0.946). This model achieved the best performance among the other but again it lacks information about the data which can help us in identifying the true relationship between the two variables.

<img src="https://github.com/rathiromil13/DS-5500-HW-2/blob/master/figures/Best.png" width="400" height ="600">

###### Figure 7: Statistics for model with Log of Mean GDP per capita and Mean Life Expectancy

![Mean GPD per capita and Mean Life Expectancy for each year](figures/Reg2.png)
###### Figure 8: Fit for the best model

The major challenge here is to somehow capture the relationship which has many dimensions and factors such as distribution of income which is not known. It is really challenging to incorporate all information in our model. It would make more sense to perform the analysis for a given country and observe the trend. It'll help us in identifying the general case as well as the outliers where we might see a negative relationship between two variables due to factors such as distribution of income.

The final equation would be Y ~ X + c where
Y: Average Life Expectancy
X: Average GDP per Capita for each year


## Solution 5

In this problem, we've to identify relationship between GDP per capita and Child Mortality rate. In general, the trend we can expect is negative relationship between GDP Growth and Child Mortality

Here's what the scatter plot looks like:
![Relationship between GDP per capita and Child Mortality](figures/C1.png)
###### Figure 9: Relationship between GDP per capita and Child Mortality

This requires log transformation for both the variables. On transforming variables, the scatter plot shows a better relationship between the two variables.
![Log GPD per capita and Log Child Mortality Rate](figures/C2.png)
###### Figure 10: Relationship between log transformed GDP per capita and Child Mortality

