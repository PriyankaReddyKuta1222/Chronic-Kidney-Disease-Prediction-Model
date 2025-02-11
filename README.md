# Chronic-Kidney-Disease-Prediction-Model
Chronic Kidney Disease (CKD) Prediction Project Report

Team Members:

Bhavana Parlupalli
Lavanya Pragada
Pavithra Kadri
Pooja Manikonda
Priyanka Reddy Kuta

Table of Contents:

Abstract
Introduction
Methods
Results
Discussion
Conclusion
References
Appendices

Abstract:

Chronic Kidney Disease (CKD) represents a significant public health issue, with early detection crucial for effective management. This project utilized logistic regression to analyze a dataset from Kaggle, comprising various clinical and demographic variables from 400 patients, to identify key predictors of CKD. Significant predictors included serum creatinine, hemoglobin, age, hypertension, and diabetes mellitus. The model demonstrated high accuracy and robustness, offering insights into early CKD detection and management. The findings underscore the potential of predictive analytics in improving patient outcomes through early intervention and targeted treatment strategies.

Introduction:

Chronic Kidney Disease (CKD) IS a critical public health concern, affecting millions of people worldwide with increased mortality (Vaidya & Aeddula, 2022). CKD is gradual loss of kidney function over time, which potentially leads to end-stage renal disease (ESRD) which requires dialysis or kidney transplantation for survival. As early stages are often asymptomatic, Early detection and intervention are very crucial for CKD (Chen et al., 2019).

The goal of our project is to use predictive modeling to identify key demographic and clinical factors that influence the development and progression of CKD. By analyzing a dataset that includes various clinical parameters and comorbidities (Chronic Kidney Disease Dataset, 2017), we want to contribute to the early detection and strategic management of CKD, potentially improving patient outcomes and reducing healthcare costs associated with advanced stages of the disease.


Methodology:

Data Collection

The foundational step in our study involved acquiring a robust dataset suitable for analyzing the progression and determinants of Chronic Kidney Disease (CKD). We sourced our data from Kaggle, which contains records for 400 patients. This dataset is rich in both numerical and categorical variables, providing a comprehensive set of features such as age, blood pressure, serum creatinine, and binary indicators for disease presence (Chronic Kidney Disease Dataset, 2017).

LINK: https://www.kaggle.com/datasets/mansoordaku/ckdisease

Data Preprocessing

•	Handling Missing Values: 

Ensuring data quality is crucial in predictive modeling, thus our initial focus was on cleaning. We addressed missing values by imputing the median for continuous variables and the mode for categorical ones. This approach minimizes distortion from outliers and maintains the central tendency of data.
•	Outlier Identification: 

We tackled outliers in our data using the Inter-Quartile Range (IQR) method. By setting upper and lower bounds based on 1.5 times the IQR, we identified and capped outliers to prevent bias in statistical analyses and predictive models. This approach maintains dataset integrity by keeping outlier influence within a reasonable range.

Data Transformation

Normalization and Scaling: 

We normalized numerical data to ensure effective model integration. This prevents variables with larger ranges from overshadowing others, particularly important in logistic regression.

Encoding Categorical Variables: 

We converted categorical variables into numerical codes using label encoding for logistic regression compatibility. This allowed essential predictors like hypertension, diabetes mellitus, and coronary artery disease to be effectively processed alongside continuous variables in predicting CKD.





Exploratory Data Analysis (EDA):

Statistical Tests: 

T-tests compared means of continuous variables between CKD and non-CKD groups, identifying significant differences. Chi-square tests assessed categorical data distributions, indicating associations with CKD presence.

Visualization Techniques: We employed a variety of visualization techniques to explore data trends and validate assumptions of our statistical tests.

•	Histograms and box plots showcased the distribution and central tendencies of variables such as age and serum creatinine levels, providing visual insights into the data skewness and presence of outliers.
•	Correlation heatmaps were used to reveal potential multicollinearity between variables, guiding our model selection and feature engineering steps.

Model Building:

	Given the binary nature of our outcome variable (presence vs. absence of CKD), logistic regression was a natural fit for our initial modeling due to its efficiency in handling binary classification problems, its interpretability, and its ability to provide probabilities as outputs, which are useful for medical decision-making.

	It was implemented using the glm() function in R, which is designed for fitting generalized linear models. The model included a comprehensive set of variables like the demographic factors such as age and gender, clinical measurements like blood pressure, serum creatinine, hemoglobin, and others, comorbid conditions including diabetes mellitus and hypertension.

Model Validation: We rigorously validated our models using several performance metrics.

	Accuracy provided a basic measure of the overall correctness of the model.
	Precision, Recall, and F1 Score offered deeper insights into the model's capability to handle imbalanced data, which is often the case in medical datasets where one class (CKD) might be less prevalent.
	The ROC Curve and Area Under the Curve (AUC) quantified the model's ability to discriminate between the two classes under various threshold settings, essential for clinical decision-making processes where sensitivity and specificity are critical.

Results:
The logistic regression model employed in this dataset aimed to discern the impact of various clinical and demographic variables on the likelihood of developing CKD. The results of this analysis provided insightful outcomes.

	Model Performance and Statistical Significance:  The logistic regression outputs indicated that several variables were statistically significant predictors of CKD. 

•	Serum Creatinine: This variable had a positive coefficient, suggesting a strong association with the likelihood of CKD. As serum creatinine levels increased, so did the probability of CKD.
•	Hemoglobin: This variable showed a negative coefficient, indicating that higher hemoglobin levels were associated with a lower probability of CKD. 
•	Age: Age was another significant predictor, with older individuals having a higher risk of developing CKD.
•	Hypertension and Diabetes Mellitus: Both conditions were positively correlated with CKD, 
	
	The model's overall accuracy and other performance metrics such as precision, recall, F1 score, and the area under the ROC curve (AUC) were commendably high. These metrics indicated excellent model performance, demonstrating the model's ability to correctly classify cases as CKD or non-CKD.

Model Diagnostics: While the model exhibited strong predictive power, initial runs highlighted convergence issues likely due to multicollinearity among predictors.

Model Diagnostics and Output: The output of the logistic regression provided several key pieces of information.

	Coefficients: The beta coefficients indicate the influence of each variable on the odds of developing CKD. Positive coefficients increase the odds of the outcome (presence of CKD), while negative coefficients decrease it.
	Significance Levels (p-values): These help determine which variables are statistically significant predictors of CKD.

	While the model exhibited strong predictive power, initial runs highlighted convergence issues likely due to multicollinearity among predictors.

Discussion:

	The results from the logistic regression model are highly informative in understanding the key factors influencing CKD development. The statistical significance of variables like serum creatinine and hemoglobin is particularly noteworthy, as these clinical measurements are routinely available and monitored in patients suspected of renal impairment. This underscores the potential utility of the model in clinical settings, where such a predictive model could aid in early screening and intervention.
	Moreover, the significant associations observed with age, hypertension, and diabetes provide a basis for targeted interventions in these higher-risk groups. For instance, managing blood pressure and blood sugar levels in patients could be emphasized as part of preventive strategies against CKD. One of the challenges encountered was the model's initial failure to converge, a common issue in logistic regression that often points to deeper data or model specification issues such as multicollinearity. Our approach to mitigating this through variable scaling and selection not only resolved the convergence issues but also enhanced the model’s performance by focusing on the most influential predictors.

Conclusion:

	The logistic regression model developed as part of this project has demonstrated a strong capacity to predict Chronic Kidney Disease using a set of clinical and demographic variables. The findings highlight significant relationships between CKD and several key predictors, with implications for early diagnosis and management of the disease.
	   The successful application of logistic regression, despite initial setbacks, showcases the model's robustness and the effectiveness of the corrective measures implemented. These insights not only enhance our understanding of CKD's determinants but also offer a valuable tool for healthcare professionals in predicting and managing this condition.
	Future work could expand on this foundation by integrating more nuanced patient data, exploring interactions between variables, or employing more complex machine learning models that might capture non-linear relationships more effectively. Additionally, longitudinal studies could provide insights into how the risk factors impact CKD progression over time, offering a dynamic view of risk that could further refine predictive accuracy.
	This project thus serves as a significant step forward in the predictive analytics of CKD, with potential implications for improving patient outcomes through earlier detection and personalized treatment strategies.

For questions or suggestions, please contact:
Priyanka Reddy Kuta : preddykuta@gmail.com




















 













 







 


 


 


 

 


 



	   










 



 


 


 




 


	 







 




	 
 

 

 

 


 

 
 

 


 

 

     
 
 
 
 
 








 
 
 
 
 
 
 
 
 
 
 
 






 
 
 
 




 
 



 
 





 
 



 
   

 
      
    
 


	  
 
 
 
 
