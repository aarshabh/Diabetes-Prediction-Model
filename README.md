**Project Report** 

**By Anish Ayare & Aarshabh Agrawal** 

**Problem Statement:** 

Diabetes is a long-term health condition impacting millions of individuals in the US. Currently, 20% of those diagnosed with diabetes and 80% of individuals with prediabetes remain unaware of their condition. A lack of awareness, especially among people in lower economic conditions, leads to severe health repercussions and imposes an economic burden exceeding $400 billion annually. Therefore, creating efficient predictive models for early detection is essential for facilitating prompt interventions, thereby reducing the effects on public health and economic stability. 

**Data Cleanup:** 

![](Aspose.Words.85723a22-ecdf-401a-a0a4-ad026a9bfa94.001.jpeg)

This heatmap is a Missing Data Correlation Heatmap, which shows the correlations between missing data across the features. It explains about missing data as follows: 

1. Color Coding: 
   1. Dark Brown (near 1.0): A strong positive correlation, meaning that if one feature is missing, the other is also likely missing. 
   1. White (near -1.0): A strong negative correlation, meaning if one feature is missing, the other is likely to be present. 
   1. Orange (near 0.0): No correlation, meaning the missingness of one feature doesn't influence the other. 
1. Diagonal: The diagonal elements have a value of 1.0 since a feature is always perfectly correlated with itself. 
1. Interpretations: 
- The heatmap indicates that for this dataset, missing values across all features appear to have a positive correlation. 
- There aren't any strong negative correlations or extreme positive correlations, meaning there are no highly predictive relationships between the missingness of features. 

**Data Visualization:**

![](Aspose.Words.85723a22-ecdf-401a-a0a4-ad026a9bfa94.002.jpeg)

Relation of diabetes with all variables 

**Strongest Positive Correlation:** Both BMI (0.29) and HighBP (0.38) exhibit a moderate positive relationship with diabetes, indicating that elevated BMI and blood pressure levels are linked to an increased prevalence of diabetes. 

**Strongest Negative Correlation:** PhysActivity (-0.16) presents a slight negative correlation, implying that higher levels of physical activity may be associated with a reduction in diabetes prevalence. 

**Other Notable Variables:** Age (0.24) reflects a positive correlation, suggesting that older individuals tend to have a higher occurrence of diabetes. Meanwhile, GenHlth (-0.41) demonstrates a strong negative correlation, signifying that individuals with poorer overall health are likely to have higher diabetes levels.** 

![](Aspose.Words.85723a22-ecdf-401a-a0a4-ad026a9bfa94.003.jpeg)

Relation among different patients 

**Strongest Correlations:** The relationship between BMI and HighBP (0.53) indicates a strong positive correlation, reinforcing the concept that increased BMI correlates with higher blood pressure among those with diabetes. Additionally, GenHlth and MentHlth (-0.17) show a slight negative correlation, suggesting that poorer general health is linked to worse mental health in diabetic patients.** 

**Complex Relationships:** PhysActivity (0.22 with MentHlth) indicates a potential positive association between physical activity and mental health in individuals with diabetes. Furthermore, High Cholesterol (0.29 with HighBP) suggests that elevated cholesterol levels might also be associated with increased blood pressure.** 

Both graphs underscore the significance of BMI, blood pressure, and general health concerning diabetes. The first graph offers a comprehensive overview of how various factors are related to diabetes, whereas the second graph delves into the correlations among individuals already diagnosed with diabetes, uncovering more intricate relationships. 

**Model Implementation:** 

1. **Naïve Bayes:**  

The accuracy score of our is 0.7225 but null accuracy score is 0.7582. So, we can conclude that our Gaussian Naive Bayes Classification model is doing a very good job in predicting the class labels. 

Now, based on the analysis that we did, we concluded that our classification model accuracy is very good. The model is doing a very good job in terms of predicting the class labels. 

But it does not give the underlying distribution of values. Also, it does not tell anything about the type of errors our classifier is making. 

**Observations:** 

In each row, the numbers sum to 1. 

There are 2 columns which correspond to 2 classes - Diabetic and non-diabetic.     Class 0 => if a person does not have diabetes. 

`    `Class 1 => if a person has diabetes. 

Importance of predicted probabilities: We can rank the observations by probability of whether a person is diabetic or non-diabetic. 

Classification threshold level 

`    `There is a classification threshold level of 0.5. 

`    `Class 0 => A person does not have diabetes < 0.5.     Class 1 => A person have diabetes > 0.5. 

![](Aspose.Words.85723a22-ecdf-401a-a0a4-ad026a9bfa94.004.jpeg)

Histogram for Naïve Bayes We can see that the above histogram is highly positive skewed. 

The first column tell us that there are approximately 4700 observations with probability between 0.0 and 0.1. 

There are relatively small number of observations with probability > 0.5. 

So, these small number of observations predict that the person have diabetes. There is almost an equal distribution of people with and without diabetes. 

2. **Decision Tree:**  

The accuracy score of our is 0.7225 but null accuracy score is 0.7225. So, we can conclude that our Decision Tree model is doing a good job, but it is not as precise as Naïve Bayes in predicting the class labels. 

![](Aspose.Words.85723a22-ecdf-401a-a0a4-ad026a9bfa94.005.jpeg)

Histogram for Decision tree 

**Observations:**

This histogram displays a bimodal distribution, exhibiting peaks in the ranges of 0.6 to 0.8 and 0.8 to 1.0. This indicates a significant number of individuals are assessed as either likely or highly likely to have diabetes.  

Consequently, the predictive model appears effective in recognizing individuals at risk, particularly those categorized as high-risk. The absence of estimated low probabilities is attributed to the limited occurrence of outcome events, which explains the observed patterns of lower frequencies in the lower probability ranges, as fewer individuals are identified as being at low risk.

**Performance Report of both models:** 

Decision Tree Accuracy: 0.7162 Naïve Bayes Accuracy: 0.7225 

Classification Report: ![](Aspose.Words.85723a22-ecdf-401a-a0a4-ad026a9bfa94.006.png)

Averages: 

|Average |Model |Precision|` `Recall|` `F1-Score|
| - | - | - | - | - |
|Macro Avg |Decision Tree|` `0.73 |0\.72 |0\.71 |
|Macro Avg |Naïve Bayes |0\.72 |0\.72 |0\.72 |
|Weighted Avg|` `Decision Tree|` `0.73 |0\.72 |0\.71 |
|Weighted Avg|` `Naïve Bayes |0\.72 |0\.72 |0\.72 |

Cross validation method- 

Decision Tree Cross-Validated Accuracy: 0.7128 Naïve Bayes Cross-Validated Accuracy: 0.7236 

**Overall Conclusion:** 

Both the models have almost the same acuracy with Decison Tree being 71.28% accurate and Naive Bayes 72.36%. Based on these results, Naïve Bayes is the slightly better model for this dataset due to its balanced and consistent performance. However, Decision Tree is still competitive and may be preferred if interpretability or class-specific optimization is required. 

Link to Dataset: https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset 
