# Machine-Learning-in-Diabetes-Prediction-and-Risk-Calculation
This project implements different machine learning algorithms in predicting diabetes and the risk of developing diabetes based on certain factors and determining which factors are important in influencing the outcome and how much they influence the outcome. 

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
- ##### ROC-AUC
- Precision
- Recall
- F-Beta (F=2)

### Interpretation Technique(s) Used: 
- SHAP (SHapley Additive exPlanations)

### Possible Next Steps: 
- Implementing an optimized (by ROC-AUC) Naive Bayes model
- Determining how other diabetes plays a role in heart disease (and maybe other diabetes)
- Maybe collect more information of those with diabetes (due to low recall score that affected F-Beta score)
- Develop some sort of app that lets users input values to see probabilistic chance of developing diabetes
- Improve best-performing model by possibly only considering the features that significantly contribute to developing diabetes

### Bibliography
- Tasin I, Nabil TU, Islam S, Khan R. Diabetes prediction using machine learning and explainable AI techniques. Healthc Technol Lett. 2022 Dec 14;10(1-2):1-10. doi: 10.1049/htl2.12039. PMID: 37077883; PMCID: PMC10107388.
- Anant Ram and Honey Vishwakarma 2021 IOP Conf. Ser.: Mater. Sci. Eng. 1116 012135
- Fregoso‑Aparicio et al. Diabetology & Metabolic Syndrome (2021) 13:148
- Zou Q, Qu K, Luo Y, Yin D, Ju Y and Tang H (2018) Predicting Diabetes Mellitus With Machine Learning Techniques. Front. Genet. 9:515. doi: 10.3389/fgene.2018.00515
- Qin, Y.; Wu, J.; Xiao, W.; Wang, K.; Huang, A.; Liu, B.; Yu, J.; Li, C.; Yu, F.; Ren, Z. Machine Learning Models for Data-Driven Prediction of Diabetes by Lifestyle Type. Int. J. Environ. Res. Public Health 2022, 19, 15027.
- Aishwarya Mujumdar, V Vaidehi, Diabetes Prediction using Machine Learning Algorithms, Procedia Computer Science, Volume 165, 2019, Pages 292-299, ISSN 1877-0509, https://doi.org/10.1016/j.procs.2020.01.047.
- K. Hasan et al.: Diabetes Prediction Using Ensembling of Different ML Classifiers
