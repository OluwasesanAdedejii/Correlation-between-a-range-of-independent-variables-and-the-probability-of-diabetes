# Correlation Between independent-variables and probability of diabetes

To identify the significant predictors, logistic regression analysis was applied, revealing that Glucose, BMI, Diabetes Pedigree Function, and Age were the most relevant factors. Furthermore, a linear regression model was employed to predict missing Glucose values based on Age, offering valuable insights into patient care and risk assessment. Overall, these findings highlight the potential of these predictors in identifying high-risk individuals and improving patient care.

# Distribution of each variable and summary statistics.

By visualising the distribution of the variables, it was noted with the exception of the variable Blood pressure ,  all the others were skewed to the left (Appendix 1). The summary statistics for the variables Glucose, Blood Pressure, Skin Thickness, Insulin, BMI, Diabetes Pedigree Function, and Age were computed using R programming language. The summary statistics revealed that Glucose had a mean of 121.69 and a standard deviation of 30.54, while Blood Pressure had a mean of 72.41 and a standard deviation of 12.38. Skin Thickness had a mean of 29.15 and a standard deviation of 10.48, whereas Insulin had a mean of 155.55 and a standard deviation of 118.78. BMI had a mean of 32.46 and a standard deviation of 6.92, while Diabetes Pedigree Function had a mean of 0.47 and a standard deviation of 0.33. Lastly, Age had a mean of 33.24 and a standard deviation of 11.76. These summary statistics provide valuable insights into the distribution and central tendency of the variables and can be used for further analysis and modeling.

Table 1: Descriptive summary of the variables

<img width="886" alt="Screenshot 2025-07-10 at 06 37 02" src="https://github.com/user-attachments/assets/ad4de088-5bfd-47f0-bf9e-c7d0513f7ccb" />

# Differences in predictor variable central tendencies based on diabetes result.

Normality checks
The Shapiro-Wilk test was used to assess the normality assumption of the Glucose, Blood Pressure, Skin Thickness, Insulin, BMI, Diabetes Pedigree Function, and Age variables in the dataset. This test was based on the recommendation by the authors González-Estrada and Cosmes  (2019) who noted this to be the most appropriate for data less than 5000.  The test revealed that all the variables violated the normality assumption (p < 0.05). This suggests that parametric tests may not be appropriate for these variables, and non-parametric tests may be more suitable. The results of the Shapiro-Wilk test highlights the importance of checking for normality in statistical analyses, as violating this assumption can lead to biased and inaccurate results.

Mann-Whitney U test 
The Mann-Whitney U test was performed to compare the distribution of glucose, blood pressure, skin thickness, insulin, BMI, diabetes pedigree function, and age between individuals with diabetes and those without. The test statistic was found to be 27393.5 for glucose, 47566.5 for blood pressure, 21930 for skin thickness, 9210.5 for insulin, for 40875 for BMI, 52769 for  diabetes pedigree function, and 41950 for age. All variables were found to be statistically significant (p < 0.05), indicating that there is a significant difference in the distribution of these variables between the two groups. Overall, these results suggest that these variables may be important predictors of diabetes and warrant further investigation. Based on the visualised differences , as shown in the results below, the individuals with diabeties were significantly higher in distribution for the variables glucose, blood pressure, skin thickness, insulin, BMI, diabetes pedigree function, and age , when compared to those without diabeties. 

Reason for boxplot visualisation
Box plots allow researchers to compare multiple groups simultaneously and to visually identify any potential differences in their distributions. Additionally, box plots can effectively represent skewed and multimodal data, which are commonly encountered in non-parametric analyses (Kehrer and Hauser, 2012). Furthermore, box plots can provide insight into the presence of potential outliers and their distribution in the data. Overall, the box plot is a valuable tool for non-parametric data visualization due to its ability to visually summarize key features of the data in a clear and informative way. 


Testing the independence of the predictor variables 
Table 2 presents the correlation coefficients for the seven variables of interest, namely Glucose, Blood Pressure, Skin Thickness, Insulin, BMI, Diabetes Pedigree Function, and Age. To account for the non-normal distribution of the variables, Spearman correlation coefficients were employed, which is a widely accepted method in the literature (Eden et al., 2022). The correlation coefficients for all variable pairs were found to be less than 0.7, which is the threshold value for multicollinearity risk according to Kim (2019). High levels of correlation between variables can introduce multicollinearity and suppress the effect of individual predictors in the regression model. Therefore, the absence of multicollinearity risk between the variables is an encouraging finding, indicating that the variables are suitable for inclusion in a linear regression model without further adjustments to address multicollinearity. A scatter plot matrix (Figure 1) was also used to visualize the relationships between the variables. Overall, the scatter plot matrix and the correlation coefficients demonstrate that the variables are independent and not highly correlated with each other.

Table 2: Spearman Correlation matrix

<img width="886" alt="Screenshot 2025-07-10 at 06 41 54" src="https://github.com/user-attachments/assets/11ad0515-cda6-4f3a-8671-ea897dc05d9f" />

<img width="886" alt="Screenshot 2025-07-10 at 06 43 03" src="https://github.com/user-attachments/assets/1cc20adf-4411-4aff-b7d2-0015d5c8dbaa" />

# Regression model to predict diabeties outcome.
In order to explore the effects of predictor variables on the diabetes outcome of patients, logistic regression was employed. This statistical test is designed to assess the ability of a set of independent variables to predict or explain a binary categorical dependent variable. The logistic regression model showed that out of the seven predictor variables, four were found to be significant predictors of diabetes outcome: Glucose, BMI, Diabetes Pedigree Function, and Age. For every one-unit increase in Glucose, the odds of having diabetes increased by 4% (OR=1.04, 95% CI: 1.03, 1.05, p<0.001). Similarly, for every one-unit increase in BMI, the odds of having diabetes increased by 7% (OR=1.07, 95% CI: 1.01, 1.13, p=0.014). The odds of having diabetes were almost three times higher for individuals with a higher Diabetes Pedigree Function score compared to those with a lower score (OR=2.94, 95% CI: 1.31, 6.86, p=0.011). For every one-year increase in Age, the odds of having diabetes increased by 5% (OR=1.05, 95% CI: 1.02, 1.08, p<0.001). Blood Pressure, Skin Thickness, and Insulin were not found to be significant predictors of diabetes outcome. These findings suggest that Glucose, BMI, Diabetes Pedigree Function, and Age are important predictors for diabetes outcome and may be useful in identifying individuals at high risk for diabetes.


#Predicting Glucose missing values using Age.
In this section, a linear regression model was fitted to the dataset with Glucose and Age variables extracted. Rows with missing Glucose values were identified and the model was used to predict their Glucose levels using the model. The model assumes that Glucose levels depend only on Age. The results showed that the predicted Glucose values for the missing entries ranged from 113.18 to 127.04. These findings can be useful in the medical field as they provide an estimate of Glucose levels for individuals with missing Glucose data, which can inform clinical decision-making and patient care.

Table 3: Predicted missing glucose values.

<img width="886" alt="Screenshot 2025-07-10 at 06 45 23" src="https://github.com/user-attachments/assets/af15d247-fb79-4cc1-9e2c-dc177a932968" />


# Conclusion 
Seeing as substituting missing values with zeros can result in skewed and erroneous estimations of statistical parameters and a loss of statistical power, dealing with the problem of missing data is crucial to ensuring the validity and reliability of statistical studies. R, a popular programming language, is one tool for dealing with missing data that often involves replacing zeros with NaN.  Before running statistical studies to compare components, it is crucial to evaluate the normalcy assumption of the data. The Mann-Whitney U test was used to compare the distribution of variables in people with and without diabetes, which is a non-parametric test that is recommended when the normality assumption is violated. This study found statistically significant differences in distributions between the two groups. Logistic regression research also found that glucose, body mass index, diabetes pedigree function, and age were all significant predictors of diabetes outcome. In order to improve clinical decision-making and patient care, a linear regression model was created to predict missing Glucose levels based on Age.


