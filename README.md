# 🫀 Heart Disease Patient Clustering (Unsupervised Learning)

## 📊 Dataset Information  
- **Source:** [UCI Machine Learning Repository – Cleveland Heart Disease Dataset](https://archive.ics.uci.edu/ml/datasets/heart+disease)  
- **Description:** Contains clinical and demographic patient features for unsupervised analysis. This project explores natural groupings of patients based solely on features—without using the target label—to support clinical interpretation and complement the supervised prediction model.  

---

## 🎯 Problem Statement  
Heart disease risk patterns are embedded in patient clinical data. This project aims to uncover **natural patient clusters** using unsupervised learning to identify **high-risk** and **low-risk** groups, validate patterns against supervised models, and provide actionable insights for healthcare decision-making.

---

## 📝 Objectives  
- Identify **natural clusters** of patients from clinical features.  
- Compare clustering algorithms: **KMeans**, **Agglomerative**, and **DBSCAN**.  
- Analyze feature patterns within each cluster.  
- Determine which clusters correspond to **low-risk** and **high-risk** patients.  
- Validate unsupervised clusters against patterns discovered in the supervised model.  

---

## ⚙️ Methods and Approach  

### 🔹 Preprocessing  
- Dropped the target column.  
- **Standardized** all numerical features.  
- **One-hot encoded** categorical variables.  
- Created **PCA components** for visualization.  

### 🔹 Clustering Algorithms  
- **KMeans** ($k = 2$ and $k = 6$)  
- **Agglomerative Clustering** (Ward linkage)  
- **DBSCAN** (density-based)  

### 🔹 Evaluation Metrics  
- **Silhouette Score**  
- **Calinski-Harabasz Index**  
- **Davies-Bouldin Score**  

### 🔹 Cluster Profiling  
- Mean values of numerical features per cluster  
- Proportions of categorical features  
- Heatmaps for feature-cluster relationships  
- **PCA visualizations**  

---

## 📈 Key Results  

### 🔹 KMeans Clustering (k = 2) — Best, most interpretable

| Cluster | Characteristics | Clinical Interpretation |
| :--- | :--- | :--- |
| **Cluster 0** | Younger, higher ST depression, lower max heart rate, more major vessels | **Low-Risk Group** (**Corresponds to Target 0: No Disease**) |
| **Cluster 1** | Older, low ST depression, higher max heart rate, fewer vessels | **High-Risk Group** (**Corresponds to Target 1: Disease**) |

> Matches supervised model patterns and provides clinically meaningful segmentation  

### 🔹 Agglomerative Clustering (k = 2)  
- Very similar to KMeans  
- Captures same high-risk vs low-risk structure  
- Slightly weaker separation by metrics  

### 🔹 DBSCAN  
- Found 2 meaningful clusters but many points marked as **noise**  
- Less suitable for this dataset  
- Clusters still corresponded to low-risk and high-risk groups  

---

## 📊 Visualizations  
- PCA cluster scatter plots  
- Cluster heatmaps (numerical features)  
- Clustered categorical distributions  
- Metric comparison tables  

---

## 🚀 Recommendations & Conclusion  

### Recommendations  
- Use **KMeans (k = 2)** for patient segmentation  
- Combine supervised predictions with unsupervised clusters for:  
    - **Risk stratification**  
    - Preventive healthcare planning  
    - Targeted patient monitoring  
- Use cluster insights to support:  
    - Explainability and transparency  
    - Early-warning systems  
- Expand dataset to improve cluster separability  

### Conclusion  
- Unsupervised clustering successfully rediscovered **high-risk** and **low-risk** patient groups  
- High-risk patients: High max heart rate, low ST depression, abnormal ECG  
- Low-risk patients: Opposite patterns  
- Confirms that heart disease risk patterns are **strongly embedded** in the dataset  
- Supports interpretability and actionable healthcare insights alongside supervised models  

