# Machine-Learning-in-Diabetes-Prediction-and-Risk-Calculation
## By Angela Cao

### About the Project: 
This project implements different machine learning algorithms in predicting diabetes and the risk of developing diabetes based on certain factors and determining which factors are important in influencing the outcome and how much they influence the outcome. 

### Data: 
The dataset used for this project is the Diabetes prediction dataset from Kaggle that has features such as age, gender, body mass index (BMI), hypertension, heart disease, smoking history, HbA1c level, and blood glucose level. The original dataset has 100,000 rows with each row representing a unique patient and 8 original features (not including diabetes which is our output variable) in the dataset. Our original dataset recorded 91,500 patients with no diabetes (diabetes = 0) and 8,500 patients with diabetes (diabetes = 1) which is quite a noticeable class imbalance. There are 4 numerical/continuous features and 4 categorical/discrete features in the dataset. The diabetes variable, which is our output variable, is a categorical/discrete variable.

### Current Approach: 
Since our original dataset is very unbalanced in terms of output (91,500 non-diabetics vs 8,500 diabetics), we'll balance out the dataset by oversampling the minority class (diabetes class) using SMOTE (Synthetic Minority Oversampling Technique) and ADASYN (Adaptive Synthetic). Since our output variable, diabetes variable, is a categorical/discrete variable, we will be taking a categorical machine learning approach with this dataset. Based on previous studies done and the need of powerful and high-performing but also efficient models/algorithms, we will implement logistic regression and tree-based models such as Random Forests and CATBoost. We will start with a baseline for all of our models implemented, and then optimize our models using Bayes Search for better prediction performance compared to our baseline performances. We then choose the best or most efficient performing model (based on ROC-AUC and training time duration) and then use SHAP to determine the most significant features in determining development of diabetes. 

### Questions: 
- What are the features that influence diabetes the most significantly and how much influence do these features have? Do each of these features have a positive or negative or neutral influence on the risk of diabetes?
- How do factors such as heart disease or gender/biological sex play a role in the development and risk of diabetes? 
- Given values of all features, what is the probabilistic chance a person will get diabetes?

### Novel Contributions: 
- Calculating probability risk of developing diabetes given the values of features
- Determining how other diseases and health conditions such as heart disease play a role in diabetes
- Determining if one gender/biological sex has an increased chance of developing diabetes
- Using training time as a determination of the best or most efficient model aside from testing phase performance (focusing on efficiency)

### Preprocessing: 
- One-Hot Encode gender feature
- Group several similar smoking_history values into one value ("former", "ever", "not current" into just "former")
- Label Encode smoking_history feature
- Normalize numerical/continuous features
- Convert age from float type to int type

### Feature Selection: 
Since number of original features was under 20 and I wanted to consider all the features in equal consideration to the development of diabetes, there was no feature selection done for now (though that can be a next step through results). 

### Dataset Classification Balancing Techniques Used: 
- SMOTE (Synthetic Minority Oversampling Technique)
- ADASYN (Adaptive Synthetic)

### Models used in this Project: 
- Gaussian Naive Bayes (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- Logistic Regression (Baseline and Optimization with Newton-Cholesky, Newton-Cg, and lbfgs solvers)
- Random Forests (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- Decision-Tree Based Bagging (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- AdaBoost (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- XGBoost (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- CatBoost (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- LightGBM (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- Gradient Boosting (Baseline and Optimization with Bayes Search of 5 iterations of 5 sections of cross-validation through ROC-AUC)

### Performance Metrics Used: 
- Accuracy
- ROC-AUC (Primary Performing Metric)
- Precision
- Recall
- F-Beta (F=2)

### Interpretation Technique(s) Used: 
- SHAP (SHapley Additive exPlanations)

### Conclusion: 
According to ROC-AUC, Gradient Boosting trained with the ADASYN version of the dataset is the best-performing model with a score of 0.99858. However, it is also the model with the longest training time with 2 hours, 55 minutes, and 5.5451 seconds even with the least amount of Bayes Search optimization iterations needed. The quickest trained model was the baseline Gaussian Naive Bayes trained with the ADASYN version of the dataset, but it is one of the worst performing models. In consideration of performance (ROC-AUC score) and training time, the best-performing model and the model we'll use for interpretation is LightGBM with a ROC-AUC score of 0.99820 and a training time of 16 minutes and 8.77944 seconds. 

Using the LightGBM trained with the ADASYN version of the dataset, we determined that the top 5 factors that influence the development and risk of diabetes are Hb1Ac level, blood glucose level, age, body mass index (BMI), and smoking history with these factors playing about equal consideration more or less to both classes (diabetes and no diabetes). While heart disease played a bit of a role in the development of diabetes, it didn't play as significant of a role as the aforementioned factors and in fact the second-least (if gender was not divided) or fourth-least (considering that gender was dummy coded during preprocessing) significant factor in the development of diabetes. 

Also, according to the interpretation, it seems like males and females are about equally as likely to develop diabetes. 

### Possible Next Steps: 
- Determining how other diabetes plays a role in heart disease (and maybe other diabetes)
- Investigate how diabetes can develop in patients who are currently diagnosed as non-diabetic in the next year or so. 
- Develop some sort of app that lets users input values to see probabilistic chance of developing diabetes
- Improve best-performing model by possibly only considering the features that significantly contribute to developing diabetes
- Implement Deep Learning/Neural Networks

### Bibliography:
- Tasin I, Nabil TU, Islam S, Khan R. Diabetes prediction using machine learning and explainable AI techniques. Healthc Technol Lett. 2022 Dec 14;10(1-2):1-10. doi: 10.1049/htl2.12039. PMID: 37077883; PMCID: PMC10107388.
- Anant Ram and Honey Vishwakarma 2021 IOP Conf. Ser.: Mater. Sci. Eng. 1116 012135
- Fregoso-Aparicio, L., Noguez, J., Montesinos, L. et al. Machine learning and deep learning predictive models for type 2 diabetes: a systematic review. Diabetol Metab Syndr 13, 148 (2021). https://doi.org/10.1186/s13098-021-00767-9
- Zou Q, Qu K, Luo Y, Yin D, Ju Y and Tang H (2018) Predicting Diabetes Mellitus With Machine Learning Techniques. Front. Genet. 9:515. doi: 10.3389/fgene.2018.00515
- Qin Y, Wu J, Xiao W, Wang K, Huang A, Liu B, Yu J, Li C, Yu F, Ren Z. Machine Learning Models for Data-Driven Prediction of Diabetes by Lifestyle Type. International Journal of Environmental Research and Public Health. 2022; 19(22):15027. https://doi.org/10.3390/ijerph192215027
- Aishwarya Mujumdar, V Vaidehi, Diabetes Prediction using Machine Learning Algorithms, Procedia Computer Science, Volume 165, 2019, Pages 292-299, ISSN 1877-0509, https://doi.org/10.1016/j.procs.2020.01.047.
- K. Hasan et al.: Diabetes Prediction Using Ensembling of Different ML Classifiers
