# Data Scientist Salaries Analysis 2023  

This repository contains two notebooks analyzing the **Kaggle Data Scientist Salaries 2023** dataset. Each notebook utilizes a different base model for prediction. The dataset used is already included in this repository.

---

## Notebooks Overview

### **KSVM-RFSVM-SVM**  
This notebook primarily employs the **Support Vector Machine (SVM)** model as the baseline predictive model. The model's performance is enhanced by incorporating two methods: **K-means clustering** and **Random Forest**.

#### **Methods Used**
- **K-means**:  
  K-means clustering is utilized as an unsupervised learning method to generate new features, enhancing the model's predictive ability.  

- **Random Forest**:  
  Random Forest is applied as a supervised learning method to rank feature importance. The top-ranked features are selected for SVM-based predictions.

#### **Results**
- K-means demonstrated the best improvement in predictive performance.  
- The standalone SVM model ranked second.  
- The Random Forest-based method performed the worst.  

#### **Potential Reasons for Random Forest's Underperformance**:
1. **Parameter Tuning Insufficiency**:  
   Although `GridSearchCV` was used for parameter optimization, the parameter range might not have included the optimal combination. Future improvements could involve more adaptive methods for parameter selection.

2. **Feature Selection Impact**:  
   Only the top features selected by Random Forest were used in the SVM model. This may have inadvertently excluded some relatively important features, impacting the model's performance. Expanding the selection range or using more appropriate feature selection methods may help.

3. **Data Suitability**:  
   Issues such as insufficient feature quantity or limited data volume might have constrained the model's performance.

---

### **KNN-SMOTE-XGBoost**  
This notebook uses the **XGBoost** model as the baseline predictive model. To address the issue of data imbalance (where U.S. companies are significantly overrepresented compared to non-U.S. companies), the **KNN-SMOTE** method is applied.

#### **Results**:
The **KNN-SMOTE** method significantly improved the model's predictive performance. Although the RMSE increased slightly, this is hypothesized to be due to noise introduced by KNN-SMOTE. Overall, the final model's results align with expectations.

---

## Dataset  
The dataset used for this analysis is sourced from **Kaggle** and is included in this repository.

---

## Results Summary  

| Model               | RMSE   | R-square |
|---------------------|--------|----------|
| SVM                 | 0.408  | 0.494    |
| KMeans-SVM          | 0.401  | 0.512    |
| RF-SVM              | 0.415  | 0.476    |
| KNN-SMOTE-XGBoost   | 0.158  | 0.668    |
| XGBoost             | 0.141  | 0.599    |

---
## Acknowledgements  

- Data Source: [Kaggle - Data Scientist Salaries 2023](https://www.kaggle.com/datasets/arnabchaki/data-science-salaries-2023)  


