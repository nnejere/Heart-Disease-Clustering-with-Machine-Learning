# Heart-Disease-Clustering-with-Machine-Learning


This repository contains the unsupervised clustering analysis of heart disease patient data using the Cleveland Heart Disease dataset. The aim is to identify natural patient subgroups based on clinical features, providing insights complementary to supervised prediction models.

Dataset

Source: UCI Machine Learning Repository – Cleveland Heart Disease Dataset

Description:
The dataset contains clinical and demographic information of patients, including age, sex, chest pain type, resting blood pressure, cholesterol, maximum heart rate, ST depression, number of major vessels affected, thalassemia type, and other heart-related measures.

Key Features

| **Column**                | **Description**                                                                                   |
| ------------------------- | ------------------------------------------------------------------------------------------------- |
| `age`                     | Age in years                                                                                      |
| `sex`                     | Sex (1 = male, 0 = female)                                                                        |
| `chest_pain_type`         | Chest pain type (0 = typical angina, 1 = atypical angina, 2 = non-anginal pain, 3 = asymptomatic) |
| `resting_bp`              | Resting blood pressure (mm Hg)                                                                    |
| `cholesterol`             | Serum cholesterol (mg/dl)                                                                         |
| `fasting_blood_sugar`     | Fasting blood sugar > 120 mg/dl (1 = true, 0 = false)                                             |
| `resting_ecg`             | Resting ECG results (0 = normal, 1 = ST-T wave abnormality, 2 = left ventricular hypertrophy)     |
| `max_heart_rate`          | Maximum heart rate achieved                                                                       |
| `exercise_induced_angina` | Exercise-induced angina (1 = yes, 0 = no)                                                         |
| `st_depression`           | ST depression induced by exercise relative to rest                                                |
| `st_slope`                | Slope of the peak exercise ST segment (0 = upsloping, 1 = flat, 2 = downsloping)                  |
| `num_major_vessels`       | Number of major vessels (0–3) colored by fluoroscopy                                              |
| `thalassemia`             | Thalassemia type (1 = fixed defect, 2 = normal, 3 = reversible defect; 0 = invalid)               |






Project Overview

The purpose of this project is to identify and profile natural patient clusters using unsupervised learning. The analysis complements prior supervised classification work and provides clinically interpretable insights into heart disease risk.

Goals

Detect natural groupings of patients based on clinical features.

Compare clusters using multiple algorithms: KMeans, Agglomerative Hierarchical Clustering, and DBSCAN.

Profile clusters to identify low-risk and high-risk patient groups.

Provide insights that align with prior supervised predictions.

Methodology

Preprocessing

Removed the target column.

Standardized numerical features.

One-hot encoded categorical features.

Optional PCA applied for visualization.

Clustering

KMeans: Tested k=2 and k=6 (silhouette and elbow methods).

Agglomerative Clustering: Ward linkage, hierarchical approach.

DBSCAN: Density-based clustering to detect high-density groups and noise.

Evaluation

Metrics: Silhouette Score, Calinski-Harabasz Index, Davies-Bouldin Score.

Cluster profiling: Numerical feature averages and categorical feature proportions.

Visualization: PCA scatter plots and feature heatmaps.

Key Results
KMeans (k=2)

Cluster 0 – Low Risk: Younger patients, higher ST depression, lower max heart rate, more major vessels affected → aligns with No Disease (0).

Cluster 1 – High Risk: Older patients, low ST depression, higher max heart rate, fewer major vessels → aligns with Disease (1).

Agglomerative (k=2)

Cluster 0 – Low Risk: Similar profile to KMeans low-risk cluster.

Cluster 1 – High Risk: Similar profile to KMeans high-risk cluster.

DBSCAN

Identified 2 dense clusters corresponding to high- and low-risk groups.

Large portion of data labeled as noise, limiting broad clinical application.

Conclusion: KMeans (k=2) provided the most clinically interpretable segmentation, validating the supervised classification patterns and revealing natural patient groupings.

Recommendations

Use KMeans (k=2) or Agglomerative (k=2) for patient segmentation.

Leverage clusters for preventive care and risk stratification.

Integrate cluster insights with supervised model predictions for enhanced interpretability.

Consider DBSCAN for identifying rare high-risk phenotypes.

Future studies could include additional diagnostic variables to improve cluster separability.
