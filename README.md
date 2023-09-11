# Machine-Learning-in-Diabetes-Prediction-and-Risk-Calculation

### About the Project: 
This project implements different machine learning algorithms in predicting diabetes and the risk of developing diabetes based on certain factors and determining which factors are important in influencing the outcome and how much they influence the outcome. 

### Data: 
The dataset used for this project is the Diabetes prediction dataset from Kaggle that has features such as age, gender, body mass index (BMI), hypertension, heart disease, smoking history, HbA1c level, and blood glucose level. There are 100,000 rows with each row representing a unique patient and 8 original features (not including diabetes which is our output variable) in the dataset. Our dataset recorded 91,500 patients with no diabetes (diabetes = 0) and 8,500 patients with diabetes (diabetes = 1) which is quite a noticeable class imbalance. There are 4 numerical/continuous features and 4 categorical/discrete features in the dataset. The diabetes variable, which is our output variable, is a categorical/discrete variable.

### Current Approach: 
Since our output variable, diabetes variable, is a categorical/discrete variable, we will be taking a categorical machine learning approach with this dataset. Based on previous studies done and the need of powerful and high-performing models/algorithms, we will implement logistic regression and tree-based models such as Random Forests. We will start with a baseline for all of our models implemented, and then optimize our models using Bayes Search for better prediction performance compared to our baseline performances. We then choose the best performing model (based on ROC-AUC) and then use SHAP to determine the most significant features in determining development of diabetes. 

### Questions: 
- What are the features that influence diabetes the most significantly and how much influence do these features have?
- Given values of all features, what is the probabilistic chance a person will get diabetes?

### Novel Contributions: 
- Calculating probability risk of developing diabetes given the values of features
- Determining how other diseases and health conditions such as heart disease play a role in diabetes

### Preprocessing: 
- One-Hot Encode gender and smoking_history features
- Convert age from float type to int type
- If it would improve performance, I did consider normalizing continuous or numerical values, but based on current model performance, that was probably not needed for now (though it would be great if anyone suggests other-wise)

### Feature Selection: 
Since number of original features was under 20 and I wanted to consider all the features as possible equal contributions to development of diabetes, there was no feature selection done for now (though that can be a next step through results). 

### Models used in this Project: 
- Logistic Regression (Baseline and Optimization with Newton-Cholesky, Newton-Cg, and lbfgs solvers)
- Random Forests (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- XGBoost (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- CatBoost (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- LightGBM (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)
- Gradient Boosting (Baseline and Optimization with Bayes Search of 15 iterations of 5 sections of cross-validation through ROC-AUC)

### Performance Metrics Used: 
- Accuracy
- ROC-AUC (Primary Performing Metric)
- Precision
- Recall
- F-Beta (F=2)

### Interpretation Technique(s) Used: 
- SHAP (SHapley Additive exPlanations)

### Conclusion: 
CatBoost with Bayes Search optimization was the best performing model based on ROC-AUC (our primary performing metric), and using SHAP, based on the model, our top five features that significantly influenced the development of diabetes are HbA1c_level, blood_glucose_level, age, bmi, and hypertension. While heart disease (the only explicit disease other than diabetes) has somewhat played a role in determining the development of diabetes, it has not played as large of a role. Thus, while heart disease can possibly play a role in developing diabetes, it does not largely determine in whether one will develop diabetes or not. 

Also, based on our performing metrics, while our best-performing model did well in not misdiagnosing (diagnoising those with no noticeable developing diabetes with the disease), it would need some improvement in detecting those with actual development of diabetes (our model did miss some patients with actual development of diabetes). This is probably due to the heavy class imbalance in our dataset where a good majority of the patients in our dataset did not have any significant development in diabetes vs noticeable development of diabetes. 

### Possible Next Steps: 
- Implementing an optimized (by ROC-AUC) Naive Bayes model
- Determining how other diabetes plays a role in heart disease (and maybe other diabetes)
- Maybe collect more information of those with diabetes (due to low recall score that affected F-Beta score)
- Develop some sort of app that lets users input values to see probabilistic chance of developing diabetes
- Improve best-performing model by possibly only considering the features that significantly contribute to developing diabetes

### Bibliography
- Tasin I, Nabil TU, Islam S, Khan R. Diabetes prediction using machine learning and explainable AI techniques. Healthc Technol Lett. 2022 Dec 14;10(1-2):1-10. doi: 10.1049/htl2.12039. PMID: 37077883; PMCID: PMC10107388.
- Anant Ram and Honey Vishwakarma 2021 IOP Conf. Ser.: Mater. Sci. Eng. 1116 012135
- Fregoso-Aparicio, L., Noguez, J., Montesinos, L. et al. Machine learning and deep learning predictive models for type 2 diabetes: a systematic review. Diabetol Metab Syndr 13, 148 (2021). https://doi.org/10.1186/s13098-021-00767-9
- Zou Q, Qu K, Luo Y, Yin D, Ju Y and Tang H (2018) Predicting Diabetes Mellitus With Machine Learning Techniques. Front. Genet. 9:515. doi: 10.3389/fgene.2018.00515
- Qin Y, Wu J, Xiao W, Wang K, Huang A, Liu B, Yu J, Li C, Yu F, Ren Z. Machine Learning Models for Data-Driven Prediction of Diabetes by Lifestyle Type. International Journal of Environmental Research and Public Health. 2022; 19(22):15027. https://doi.org/10.3390/ijerph192215027
- Aishwarya Mujumdar, V Vaidehi, Diabetes Prediction using Machine Learning Algorithms, Procedia Computer Science, Volume 165, 2019, Pages 292-299, ISSN 1877-0509, https://doi.org/10.1016/j.procs.2020.01.047.
- K. Hasan et al.: Diabetes Prediction Using Ensembling of Different ML Classifiers
