# Heart-Disease-Clustering-with-Machine-Learning


# 🫀 Heart Disease Patient Clustering (Unsupervised Learning)

This repository contains the **unsupervised machine learning analysis** of the **Cleveland Heart Disease dataset**.

The goal is to uncover **natural patient groupings** based solely on clinical features—without using the target label—to support deeper clinical interpretation and complement the supervised prediction model built earlier.

---

## 📘 Dataset Information

* **Source:** UCI Machine Learning Repository
* **Dataset:** Cleveland Heart Disease Dataset
* **Description:** Contains demographic and clinical features including age, sex, chest pain type, cholesterol, blood pressure, ECG results, ST depression, maximum heart rate, thalassemia type, and more.

---

## 🔎 Features Used in This Clustering Project

| Column | Description |
| :--- | :--- |
| **age** | Age in years |
| **sex** | Sex (1 = male, 0 = female) |
| **chest\_pain\_type** | Chest pain type (0 = typical angina, 1 = atypical angina, 2 = non-anginal pain, 3 = asymptomatic) |
| **resting\_bp** | Resting blood pressure (mm Hg) |
| **cholesterol** | Serum cholesterol (mg/dl) |
| **fasting\_blood\_sugar** | Fasting blood sugar > 120 mg/dl (1 = true, 0 = false) |
| **resting\_ecg** | Resting ECG results (0 = normal, 1 = ST-T wave abnormality, 2 = left ventricular hypertrophy) |
| **max\_heart\_rate** | Maximum heart rate achieved |
| **exercise\_induced\_angina** | Exercise-induced angina (1 = yes, 0 = no) |
| **st\_depression** | ST depression induced by exercise relative to rest |
| **st\_slope** | Slope of the peak exercise ST segment (0 = upsloping, 1 = flat, 2 = downsloping) |
| **num\_major\_vessels** | Number of major vessels (0–3) colored by fluoroscopy |
| **thalassemia** | Thalassemia type (1 = fixed defect, 2 = normal, 3 = reversible defect; 0 = invalid) |

---

## 📌 Project Overview

This work extends the earlier supervised heart disease prediction project.

In that earlier stage, the dataset underwent:
* In-depth cleaning
* Exploratory data analysis (**EDA**)
* Feature engineering
* Model training & evaluation
* Deployment

This clustering project focuses on what the data reveals on its own, **without labels**.

---

## 🎯 Objectives

* Identify **natural clusters** of patients using unsupervised learning.
* Compare different clustering algorithms (**KMeans**, **Agglomerative**, **DBSCAN**).
* Analyze feature patterns within each cluster.
* Determine which clusters correspond to **low-risk** and **high-risk** patient groups.
* Validate clustering results against patterns discovered in the supervised model.

---

## 🛠️ Methodology

### 1. Preprocessing

* Dropped the target column.
* **Standardized** all numerical features.
* **One-hot encoded** categorical variables.
* Created **PCA components** for visualization.

### 2. Clustering Algorithms

* **KMeans** ($k = 2$ and $k = 6$)
* **Agglomerative Clustering** (Ward linkage)
* **DBSCAN** (density-based)

### 3. Evaluation Metrics

* **Silhouette Score**
* **Calinski-Harabasz Index**
* **Davies-Bouldin Score**

### 4. Cluster Profiling

* Mean values of numerical features per cluster.
* Proportions of categorical features.
* Heatmaps for feature-cluster relationships.
* **PCA visualizations**.

---

## 🧩 Key Results

### 🔹 KMeans Clustering (k = 2) — Best, most interpretable

| Cluster | Characteristics | Clinical Interpretation |
| :--- | :--- | :--- |
| **Cluster 0** | Younger, higher ST depression, lower max heart rate, more major vessels. | **Low-Risk Group** (**Corresponds to Target 0: No Disease**) |
| **Cluster 1** | Older, low ST depression, higher max heart rate, fewer vessels. | **High-Risk Group** (**Corresponds to Target 1: Disease**) |

> **✓ Matches supervised model patterns**
> **✓ Most clinically meaningful segmentation**

### 🔹 Agglomerative Clustering (k = 2)
* Very similar to KMeans.
* Captures the same **high-risk vs low-risk structure**.
* Slightly weaker separation based on metrics.

### 🔹 DBSCAN
* Found 2 meaningful clusters, but many points marked as **noise**.
* Not suitable for this dataset’s structure.
* Clusters still corresponded to low-risk and high-risk groups.

---

## 📊 Visualizations

The notebook includes:

* PCA cluster scatter plots
* Cluster heatmaps (numerical features)
* Clustered categorical distributions
* Metric comparison tables


---

## ✔️ Recommendations

### Summary
The clustering analysis uncovered distinct **high-risk** and **low-risk** patient groups that closely match the supervised model’s findings. **KMeans ($k = 2$) provides the most robust and clinically useful segmentation.**

### Recommendations
* Use **KMeans ($k = 2$)** for ongoing patient segmentation.
* Combine supervised predictions with unsupervised clusters for:
    * **Risk stratification**
    * Preventive healthcare planning
    * Targeted patient monitoring
* Use cluster insights to support:
    * Explainability
    * Model transparency
    * Early-warning systems
* Consider expanding the dataset to improve cluster separability.

---

## 🏁 Conclusion

The clustering analysis successfully **rediscovered the same patient subgroups** identified by the supervised classification model.

This demonstrates that:
* Heart disease risk patterns are **strongly embedded** in the dataset.
* Unsupervised learning can independently reveal **clinically meaningful clusters**.
* **High-risk patients** share common characteristics: **High maximum heart rate, Low ST depression, Abnormal ECG**.
* **Low-risk patients** show the opposite patterns.

Overall, this work **strengthens confidence in the predictive model**, adds interpretability, and provides **actionable segmentation** for healthcare decision-making.
