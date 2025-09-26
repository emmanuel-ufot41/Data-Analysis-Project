
STEP 1: SKEWNESS

1.1 DEFINITION: Skewness in financial analytics and statistics is a measure of the degree of asymmetry in a dataset. The graph of a normal distribution forms a complete bell curve, where the mean, median, and mode are all equal. (kim, 2013). However, the presence of extreme values shift the distribution from its mean, it loses its symmetry and becomes skewed.
Skewness can be defined by
 
 
Skew is the third moment about the mean.
1.2 DESCRIPTION: A distribution loses its symmetry in the following ways: To the left (left-skewed or Negative skewness) and to the right (right-skewed or positive skewness).
•	Positive Skewness: If a distribution is skewed to the right, the extreme data values are larger, causing the mean to be greater than the median.
See Figure 1: Histogram showing positive skewness
•	Negative Skewness: Conversely, if a distribution is skewed to the left, the extreme data values are smaller, making the mean less than the median.
See Figure 2: Histogram showing Negative skewness
1.3 DEMONSTRATION: From the loan dataset used for this section, we calculated the skewness of revol_util feature. The basic parameters are:
1.	Total Number of data points (N) = 9578
2.	Mean of revol_util feature (X) = 46.7992
3.	Sum of (Xi – X)**3 =  14028983.47305
4.	Cube of the standard deviation = 24425.3921
Skewness = (14028983.47305)/9577*24425.3921 = 0.06
Note that the value of skewness ranges from negative infinity to positive infinity. The closer the value of skewness to zero (0), the symmetrical the distribution is.
1.4 DIAGRAM: The following charts were used to visualize skewness:
1.	Figure 1: Distribution of simulated_negative_Skewness 
2.	Figure 2 Distribution of log. Annual.inc
3.	Figure 3: Distribution of days.with.cr.line
4.	Figure 4: Distribution of inq. last. 6mths

1.5 DIAGNOSIS: The following methods can help in testing for skewness in any distribution:
1.	Calculating skewness coefficient: skewness coefficient can be calculated using pearson’s median skewness, pearson’s mode skewness and Shapiro-wilk test 
2.	Inspecting visuals like histogram.

1.6 DAMAGE: Skewness can be detrimental to statistical models and analyses in the following way:
i)	Baised  prediction
ii)	Inaccurate prediction of central tendency
iii)	Reduced model performance.

Many financial models that attempt to predict the future performance of an asset assume a normal distribution. If the data are skewed, this model will always underestimate skewness risk in its predictions. The more skewed the data, the less accurate this financial model will be. West SG (1995)

1.7 DIRECTIONS: To work with skewed data, we have to transform the data. Transformation can help to normalize the skewed data. The following transformation method are best for skewed data:
i)	Logarithmic differencies.
ii)	Square root transformation.
iii)	Power transformation










STEP 2: KURTOSIS AND HETEROSCEDASTICITY
2.1 DEFINITION: Kurtosis is a statistical measure that can tell us how heavy the tails of a distribution is compared to the tail of a normal distribution. The kurtosis of a normal distribution is 3. Kurtosis identifies whether the tails of a given distribution contain extreme values. Heteroscedasticity is simply a situation where the variance of the error term in a regression model is not constant. Aytug (2012)
In statistics, high kurtosis can be caused by conditional heteroscedasticity. Conditional heteroscedasticity is a type of heteroscedasticity where the variance of the error term changes across different values of the independent variable. Cribari-Neto  (2004) 
Kurtosis can mathematically be defined as
  
Where:
•	  is the standardized fourth moment
•	  is the unstandardized central fourth moment
•	  is the standard deviation
 2.2 DESCRIPTION: According to Aytug (2012), a distribution can exhibit in the following forms: 
1.	Mesokurtic: A mesokurtic distribution shows an excess kurtosis (Excess Kurtosis = Kurtosis – 3) of zero or close to zero.

2.	Leptokurtic: This shows a positive excess kurtosis. The leptokurtic distribution shows heavy tails on either side, indicating large outliers.

3.	Platykurtic: A platykurtic distribution shows a negative excess kurtosis. The kurtosis reveals a distribution with flat tails. The flat tails indicate the small outliers in a distribution.
 
2.3 DEMONSTRATION: From the simulated data used for this section, we calculated the kurtosis of the features. The basic parameters are recorded in the table below:

Features	Mesokurtic	Leptokurtic	Platykurtic
Mean	0.00	0.03	-0.01
Median	-1.19	-1.19	-1.19
Standard Deviation	1.00	1.43	1.15
Kurtosis	3.03
	
5.86	1.81


2.4 DIAGRAM: The following charts were used to visualize the three (3) different types of kurtosis:
1.	Figure 2: Distribution of mesokurtic 
2.	Figure 3: Distribution of leptokurtic
3.	Figure 4: Distribution of platykurtic

2.5 DIAGNOSIS: We can check the kurtosis of a distribution with the following methods:
1.	Jarque-Beta: This test helps us to ascertain the degree at which our data deviates from a normal distribution. The greater the value of Jarque-beta statistic, the greater the deviation from the normal distribution
2.	Skewness-Kurtosis All Normality Test: This is also called D'Agostino Chi2 Omnibus test. This test the degree of deviation of a distribution from a normal distribution by comparing the skewness and kurtosis of that distribution.
Since a normal distribution has skewness of 0 and kurtosis of 3, the test is based on the difference between the data's skewness (0) and the kurtosis (3).

The test rejects the hypothesis of normality when the p-value is less than or equal to the significant value (0.05).  Failing the normality test allows you to state with 95% confidence the data does not fit the normal distribution.  Passing the normality test only allows you to state no significant departure from normality was found. 

2.6 DAMAGE: Clear statement of the damaged caused by the problem 

In finance, the platykurtic distribution of the investment returns is desirable for investors because there is a small probability that the investment would experience extreme returns.

On the other hand, leptokurtic distribution shows that the investment returns may be prone to extreme values on either side. Therefore, an investment whose returns follow a leptokurtic distribution is considered to be risky. West SG (1995)

2.7 DIRECTIONS:  From our problem statement, we know that higher kurtosis is a serious challenge to investors. Higher kurtosis posts problem of conditional heterosceasticity. Kim (2013) highlighted some of ways of controlling conditional heteroscedasticity to include the following methodologies: 
1.	Square root transformation
2.	Logarithmic transformation
3.	Outlier removal
4.	Box-Cox transformation



















STEP 3: ADDRESSING SENSITIVITY TO OUTLIERS

3.1 DEFINITION:
Outliers are extreme values that we have within the dataset. The outlier data points vary greatly from the expected values—either being much larger or significantly smaller. Barnett (1994)
An outlier is “an observation that deviates so much from other observations as to arouse suspicion that it was generated by a different mechanism” (Hawkins 1980).

A data point is an outlier if it is more 1.5*IQR above the third quartile or below the first quartile. Thus we mean that Q1 – 1.5*IQR and Q3 + 1.5*IQR are lower and higher outliers respectively. (IQR is the Interquartile Range, Q1 is the lower quartile and Q3 is the upper quartile).
Hawkins (1980) further mentioned that issues of outliers can occur in a dataset due to or poor sampling. It can occur naturally through variability, or they can be the result of issues like human error, fault in measuring equipment. In spite of the cause, outliers can have a big impact on statistical analysis and accuracy of our model because they impact calculations like mean and standard deviation. 

3.2 DESCRIPTION: 
Outliers can skew hypothesis tests because they impact parameters like mean and standard deviation. The scatter plot below helps us to visualize existing outliers in our dataset. 

3.3 DEMONSTRATION:
Consider the scores of 50 students in a data science test given as 

Scores	84	89	35	82	71	74	70	91	42	100	81	51	87	98	65	1120
Num. of students	5	1	3	3	4	4	2	 1	3	7	8	4	1	 2	2	50
 TOTAL	

Mean = Total Score / Number of Students
Mean = (84 + 89 + 35 + 82+…+ 65) / 50 = 1,120 / 50 = 22.5

Though we have a lower outlier (35) in the data, we would like to introduce a more visible higher outlier score “1000”. (Obviously, there’s no way a student can have 1000%
score in a test. We only use it in this context to demonstrate outlier influence).

The score therefore becomes:

|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|

| Scores	| 84 |	89 |	35	| 82	| 71	| 74	| 70	| 91	| 42	| 100 |	81	| 51	| 87	| 98	| 65	| 1000	| 2120  |   
| Num. of students	| 5	| 1	| 3	| 3	| 4	| 4	| 2	| 1	| 3	| 7	| 8	| 4	| 1	|  2	| 2	| 3	| 53 |  

Mean = (84 + 89 + 35 + … + 65 + 1000) / 53 = 2120 / 53 = 40.0

Observe how the presence of outlier score (1000) changed the mean value from 22.5 to 40. Outliers can as well reduce the mean (or Standard deviation) of the score if the 
outlier score were significantly small.

3.4 **DIAGRAMS:** The following visuals were created to demonstrate the presence of outlier in our dataset:
1.	Figure 1: Shows a violin plot of student scores without outliers.
2.	Figure 2: Shows box plot of student scores without outliers.
3.	Figure 3: Shows a violin plot of student scores with outliers.
4.	Figure 4: Shows a box plot of student scores with outliers.
5.	Figure 5: Distribution plot of students’ scores with outliers
6.	Figure 6: Distribution plot showing the log of students’ score
7.	Figure 7: Histogram of the Students’ scores

3.5 **DIAGNOSIS:** In finance and analytics, most methods used is mostly based on the nature of underlying distribution. According to Belsley (1980), we can recognize or test 
    that the problem of outliers exists with the following methods:
1.	Use of Visualization techniques. Plots such as box plot, violin plot and histogram can easily help to identify data points that are outliers.
2.	Use of outlier formula. Outlier formula helps in recognizing the higher and the lower outliers. Using box plot, higher outliers appears around the upper fence while lower
    outliers appears around the lower fence. The formula for the upper fence is Q3 + 1.5(IQR), and the formula for the lower fence is Q1 - 1.5(IQR). 	

3.6 **DAMAGE:** To clear ascertain the damages caused by the presence of outliers, let us run a linear regression model with our datasets (df : without outliers and df2: with outliers), 
then we will compare their fitness and accuracy in terms of AIC values, BIC values, residuals of the intercept, standard error of the independent variables, skewness and Kurtosis.

|  Parameters |  	With Outliers | Without Outliers  |   
|---|---|---|
| Data  | Df2  |  Df |   
| AIC and BIC	 |  248.0 and 249.8	 | 150.0 and 151.6  |  
| Residuals  |  16 |  15 | 
| Std error of intercept | 110.356 |	9.365 |
| Std error of indep. variable | 27.637 |	2.316 |
| Skew | 3.810	| - 0.540 |
| Kurtosis |	15.718	| 2.400 |
| p-values	| 0.807	| 0.977 |

3.7 **DIRECTIONS**: The following models or methodologies are Suggested way for handling outliers in a given dataset. These method also depend on the underlying distribution. 
1.	**Drop Method**: By using dropping method, the row that contains the outlier(s) is deleted from the dataset. This is also not a better practice as it leads to loss of data. 
2.	**TRANSFORMATION:** By using transformation method, we simply transform the variable in such a way as to induce normality, then we set thresholds to identify extreme values
    Transformation involves taking the logarithm of the variable of interest. The log operation can “shrink” the outlier values more, so that skewed distributions
    variable become more symmetrical and closer to a Normal distribution.
3.	**IMPUTATION METHOD:** This involves replacing or changing the outlier values with the mean or median the values of outliers.
   
4.	**USE ROBUST ESTIMATION TECHNIQUES (M-estimation)**. A common solution is to use robust measures of scale and location to set the threshold for outliers. This is done
    by replacing the sample average 𝑥 with a robust estimator (e.g. the median), and the standard deviation 𝑠 with a robust estimator. While there is no agreement on the
    best method, the most popular option among analyst is the median absolute deviation (MAD).
 
3.7.1 **SUMMARY:** An outlier is an observation “that appears to deviate markedly from other members of the sample in which it occurs” (Grubbs, 1969). Note that in this 
context, we focus on univariate outliers, those found when looking at a distribution of values in a single dimension (e.g. Students’ scores).

“A data analyst should use various techniques to visualize and identify outliers before deciding whether they should be dropped, kept, or transformed”. (John 1999)

## STEP 4: MODELING NON-STATIONARITY AND FINDING A UNIT ROOT TESTING

4.1 DEFINITION: Stationarity is a property or feature of a dataset where the fundamental statistical characteristics of the dataset (usually a time series) 
like the mean, variance, and autocorrelation, remains unchanged over time. Non-stationarity is a huge problem in time series analysis. If you’re trying to identify 
trends and use statistical models on time series, you want the opposite you will want your data to be stationary. Tsay (2000)

4.2 **DESCRIPTION:** The following are the different form of non-stationary processs
1.	Random walk without drift
2.	Random walk with drift
3.	Deterministic trend
   
“These non-stationary process may be helpful in the transformation of the non-stationary process.” Tsay (2000)
4.3	**DEMONSTRATION:** From the simulated data used in this section, the following statistics were obtained both before and after transformation:

**Statistics	Before Transformation	After Transformation**
	
| ADF statistics  |  -0.05606	|  -3.64080 |   
|---|---|---|
| **p-value** |  0.95364 | 0.05027  |  
|**Critical value at 1% confidence interval**| -3.58857  | -3.62092  |   
| **Critical value at 5% confidence interval** |  -2.92989 | -2.94354  | 
| **Critical value at 10% confidence interval** | -2.60318	| -2.61040 |

Observe that the p-value of the non-stationary time series is greater than 0.05 and the p-value of the transformed time series data is 0.05. This is the major bases for stationarity.  

4.4 **DIAGRAM:** The following charts were used to visualize non-stationary and stationary data:
1.	Generated Non-stationary Data
2.	Transformed stationary Data 

4.5 **DIAGNOSIS:** The following methods are useful for testing for non-stationarity in any distribution:

1.	**Visualizations**
The most basic methods for stationarity detection rely on plotting the data and visually checking for trend and seasonal components. Trying to determine whether a stationary
process generated a time series just by looking at its plot is a stressful task. There are basic properties of non-stationary data that we can look for. Agiakoglou (1992)

3.	**Statistical Unit root Test:** The unit root statistical tests which are mostly in use are:
   
i)	Augmented Dickey-Fuller (ADF) Test
ii)	Kwiatkowski-Phillips-Schmidt-Shin (KPSS) Test
iii)	Phillips-Perron (PP) test:

“The ADF test focuses on detecting unit roots, which indicate non-stationarity, while the KPSS test checks for trend stationarity” (Agiakoglou 1996)

4.6 **DAMAGE**
Non-Stationary data possess non-stability into the mean and variance in long run. This means that variance goes to infinity as time goes infinite and mean value never 
become stable on one value as time passes.

Non-Stationary data can’t be predicted, cannot give a precise conclusion, can’t be modeled and forecasted, it can create spurious relationships due to presence of 
non-stability factors that lead to variation in the values of statistical properties like mean, variance over time Agiakoglou (1996). 

4.7 **DIRECTIONS**: To get consistent and reliable outcome of non-stationary data, there is a need to transform non-stationary data into stationary data. Under stationarity 
condition forecasted value will be consistent and reliable.

**REFERENCES**
Hawkins, Douglas M. Identification of outliers. Vol. 11. London: Chapman and Hall, 1980.

Grubbs, Frank E. "Procedures for detecting outlying observations in samples." Technometrics 11, no. 1 (1969): 1-21.

Agiakoglou C, Newbold P.  Empirical evidence on Dickey-Fuller type tests. Journal of Time Series Analysis 6: 471–483. 1992.
Agiakoglou C, Newbold P. The balance between size and power in Dickey-Fuller tests with data-dependent rules for the choice of truncation lag. Economics Letters 52: 229–234. 1996

Cribari-Neto, F. Asymptotic inference under heteroskedasticity of unknown form. Computational Statistics and Data Analysis, 45:215233. 2004.

Kim, Hae-Young. Statistical Note for clinical researchers: Assessing normal distribution (2) using skewness and kurtosis. 38.1.52, rde., 2013

Davidson, R. and Flachaire, E. The wild bootstrap, tamed at last. Journal of Econometrics, 146:162169, 2008.

Tsay, R. S., Time Series and Forecasting: Brief History and Future Research, Journal of the American Statistical Association, Vol.95, 2000, pp. 638-643.
West SG, Finch JF, Curran PJ. Structural equation models with non-normal variables: problems and remedies. In RH Hoyle (Ed.). Structural equation modeling: Concepts, issues and applications. Newbery Park, CA: Sage; 1995. p56-75.

Aytug, Z. G., Rothstein, H. R., Zhou, W., & Kern, M. C. Revealed or concealed? Transparency of procedures, decisions, and judgment calls in meta-analyses. Organizational Research Methods, 15,103-133. 2012

Barnett, V., & Lewis, T. Outliers in statistical data (3rd ed.). New York, NY. 1994.

John Wiley. Becker, C., & Gather, U. The masking breakdown point of multivariate outlier identification rules. Journal of the American Statistical Association, 94, 947-955. 1999.

 Belsley, D. A., Kuh, E., & Welsh, R. E. Regression diagnostics: Identifying influential data and sources of collinearity. New York, NY: John Wiley. 1980.

