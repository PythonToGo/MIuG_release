# Fairness of Predictive Modelling Based on Traffic Check Data

## Overview

This project aims to design a prediction model and evaluate its fairness using the North Carolina Policing Dataset. The focus is on predicting arrest decisions and assessing the fairness of these predictions based on gender, age, and race. The study includes data preprocessing, model selection, and fairness evaluation using various statistical methods.

## Table of Contents

1. [Abstract](#abstract)
2. [Data Preprocessing](#data-preprocessing)
3. [Binary Classifier Selection](#binary-classifier-selection)
    - [Logistic Regression](#logistic-regression)
    - [K-Nearest Neighbors (KNN)](#k-nearest-neighbors-knn)
    - [Fine-tuned K-Nearest Neighbors](#fine-tuned-k-nearest-neighbors)
    - [Dummy Classifier: Performance Comparison](#dummy-classifier-performance-comparison)
4. [Model Selection](#model-selection)
5. [Features for Fairness Check](#features-for-fairness-check)
    - [Independence](#independence)
    - [Separation](#separation)
    - [Sufficiency](#sufficiency)
6. [Conclusion](#conclusion)
7. [Appendix](#appendix)
8. [References](#references)

## Abstract

This research designs a prediction model to evaluate its fairness in arrest decisions based on the North Carolina Policing Dataset. The study compares logistic regression, KNN, and fine-tuned KNN, adopting a fine-tuned KNN with an optimal accuracy of 0.95. Factors like gender, age, and race are evaluated for their impact on fairness. The study found a correlation between these factors and arrest decisions, aiming to ensure high independence and accuracy by adjusting thresholds.

## Data Preprocessing

- **Missing Values:** Handled by filling missing values with the mean or dropping columns with many missing values.
- **Date-Time Conversion:** 'Stop date' column was converted and split into year, month, day, and day of the week.
- **Column Dropping:** Irrelevant columns like 'state' and 'district' were dropped.
- **Label Encoding and One-Hot Encoding:** Categorical data was encoded for model training.
- **Correlation Checks:** Checked for multi-collinearity and dropped highly correlated columns.

## Binary Classifier Selection

### Logistic Regression

- **Performance Metrics:** High accuracy with an AUC of 0.97 and balanced precision and recall.
- **Confusion Matrix:** Showed high true positive and true negative rates.

### K-Nearest Neighbors (KNN)

- **Default and Fine-tuned:** Fine-tuned KNN showed improved accuracy with an optimal K value of 34, achieving an accuracy of 0.95.
- **Performance Comparison:** KNN had an AUC of 0.91 before tuning and 0.92 after tuning.

### Dummy Classifier: Performance Comparison

- **Baseline Performance:** Low accuracy with an AUC of 0.5, indicating poor performance compared to logistic regression and KNN.

## Model Selection

The fine-tuned KNN model was chosen as the final model due to its high accuracy and performance metrics compared to other models.

## Features for Fairness Check

### Independence

- **Chi-squared Test:** Found correlations between arrest decisions and features like gender, age, and race.

### Separation

- **Chi-squared Statistic:** Measured separation with 'driver race Asian' showing the highest separation.

### Sufficiency

- **Information Entropy:** Evaluated sufficiency by comparing target and conditional information entropy.

## Conclusion

The study successfully designed a prediction model with a focus on fairness. While the model showed correlations with age, gender, and race, optimal thresholds were adjusted to mitigate unfair impacts. Further research is needed to confirm the model's fairness using additional data.

## Appendix

Detailed preprocessing steps, including Python functions used, can be found in the appendix of the report.

## References

1. A. L. et al. Machine Learning: A First Course for Engineers and Scientists. Cambridge University Press, 2022.
2. J. Z. et al. Is chatgpt fair for recommendation? evaluating fairness in large language model recommendation. arXiv, 2305.07609v2, July 2023.
3. M. Kuhn. Applied predictive modeling. Springer, 2013.

## Authors
- Taeyoung Kim (ty.kim@tum.de, pythontogoplease@gmail.com), Technische Universität München, Fakultät für Elektrotechnik und Informationstechnik
- Mingi Kang(mingi.kang@tum.de ), Technische Universität München, Fakultät für Elektrotechnik und Informationstechnik

