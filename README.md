# M259: Machine Learning - Personal Key Indicator of Heart Disease

**Author:** Sara C. Ramirez  
**Date:** 30/09/22  
**Course Code:** M259  

---

## Table of Contents

1. [Business Understanding](#business-understanding)
2. [Data Understanding](#data-understanding)
3. [Exploratory Data Analysis (EDA)](#eda-durchführen)
4. [Data Preparation](#data-preparation)
5. [Modeling](#modeling)
6. [Summary](#zusammenfassung)

---

## Business Understanding <a name="business-understanding"></a>

This project aims to identify factors influencing heart diseases and whether individuals with heart diseases share certain characteristics.

## Data Understanding <a name="data-understanding"></a>

The dataset "Personal Key Indicators of Heart Disease" contains 18 columns:

| Name              | Description                                     | Data Type |
|-------------------|-------------------------------------------------|-----------|
| HeartDisease     | Indicates whether a person has heart disease   | Object    |
| BMI               | Body Mass Index of the person                  | Float64   |
| Smoking           | Whether person smoked more than 100 cigarettes | Object    |
| AlcoholDrinking   | Whether person drinks 7 or 14 alcoholic drinks | Object    |
| Stroke            | Whether person had a stroke                    | Object    |
| PhysicalHealth    | Days of physical discomfort in the last 30 days| Float64   |
| MentalHealth      | Days of mental discomfort in the last 30 days  | Float64   |
| DiffWalking       | Difficulty in walking                          | Object    |
| Sex               | Male or female gender                          | Object    |
| AgeCategory       | 13 different age categories                    | Object    |
| Race              | Race or ethnicity categories                   | Object    |
| Diabetic          | Whether person has diabetes                    | Object    |
| PhysicalActivity  | Whether person did sports in the last 30 days  | Object    |
| GenHealth         | General well-being                             | Object    |
| SleepTime         | Average hours of sleep                         | Float64   |
| Asthma            | Whether person has asthma                      | Object    |
| KidneyDisease     | Whether person has kidney disease              | Object    |
| SkinCancer        | Whether person has skin cancer                 | Object    |

## Exploratory Data Analysis (EDA) <a name="eda-durchführen"></a>

### Data Import

The dataset was imported from Kaggle as a CSV file.

### Analysis

The dataset comprises 18 columns and 319795 rows.

### Data Cleansing

There are numerous 'object' data types that need to be cleaned to make them usable.

### Univariate Analysis

Most individuals do not have heart disease.

### Bivariate Analysis

#### Heart Disease - Age Category

As age increases, the prevalence of heart disease also increases. Although there are fewer individuals in age categories 12 and 13, it is noticeable that the number of affected individuals is higher compared to other age categories.

#### Heart Disease - Asthma

Asthma does not appear to be a significant factor.

## Hypotheses

1. Individuals with a BMI over 25 (considered overweight) tend to have a higher tendency towards heart disease.
2. Older age categories are assumed to have a higher risk of heart disease.
3. Smoking and/or drinking may increase the likelihood of developing heart disease over one's lifetime.
4. Men tend to be more susceptible to heart disease.

### Hypothesis Testing

#### Hypothesis 1:

20,663 out of 27,373 individuals with heart disease have a BMI higher than 25, indicating that 75.49% of those with heart disease are overweight.

#### Hypothesis 2:

This was already evident in the data analysis, showing that 23,975 out of 27,373 individuals with heart disease are older than 60.

#### Hypothesis 3:

58.72% of individuals with heart disease either smoke or have smoked more than 100 cigarettes. However, only 4.71% consume more than 7 or 14 alcoholic drinks per week.

#### Hypothesis 4:

Although men tend to have a higher tendency towards heart disease, it is not significantly conclusive.

## Data Preparation <a name="data-preparation"></a>

Several columns required preprocessing. All columns with 'Yes' or 'No' responses were encoded as 0 or 1. Age categories were simplified to 1-13. Some columns were dropped: 'Race' due to inadequate representation, 'GenHealth' incorporated into 'PhysicalHealth' and 'MentalHealth', 'Stroke' as it may occur due to various reasons, and 'DiffWalking' as it correlates with age. Duplicates and empty records were removed.

## Modeling <a name="modeling"></a>

The dataset was utilized for classification. The DecisionTreeClassifier achieved 86% accuracy, LogisticRegression up to 91%, LinearDiscriminantAnalysis and KNeighborsClassifier both reached 90%, and GaussianNB achieved approximately 85% accuracy. Age category and smoking emerged as significant factors.

### Model Limitations:

1. Imbalanced distribution of age categories.
2. Race may not significantly influence outcomes.
3. Gender disparity requires further investigation.

## Summary <a name="zusammenfassung"></a>

This project utilized a Kaggle dataset and involved extensive data analysis and cleansing. Challenges were encountered during encoding due to the need for transformations in most columns. Classification was employed, with LogisticRegression exhibiting the highest accuracy at 91%. Age category and smoking were identified as major factors influencing heart disease. Model limitations include age category distribution, race, and gender disparities. Further investigation is warranted to address these issues.
