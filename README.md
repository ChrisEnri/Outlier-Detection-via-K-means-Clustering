![R](https://img.shields.io/badge/language-R-blue)

# 📊 Outlier Detection via K-means Clustering 🚀
## Author: Christian Amaro

## Focus: Data Consistency Analysis & Anomaly Detection.

This project implements a robust anomaly detection system leveraging unsupervised machine learning. The primary objective is to identify records that deviate from group behavior within a multivariate dataset, enabling precise statistical and visual auditing.

📌 Project Overview
In institutional data analysis, detecting errors or extraordinary records is vital for data integrity. This project utilizes the K-means algorithm to cluster similar observations and calculates the Euclidean distance of each point relative to its assigned cluster centroid. Observations exceeding a critical threshold of standard deviations are flagged as outliers.

## 🛠️ Tech Stack & Libraries
Language: R 

Data Manipulation: tidyverse, dplyr, readxl

Algorithms & Diagnostics: cluster, factoextra, KMEANS.KNN

Visualization: plotly (Interactive 3D), ggplot2


## ⚙️ Analytical Workflow. 

### 1. Data Ingestion & Feature Selection 

📂Records are extracted from the Survey source (Excel). We strategically select key metrics (US111_02_NORM, US111_03_NORM, US112_01_NORM) while maintaining unique identifiers (ID_CA2022_UP) to ensure full traceability of the findings.

### 2. Statistical Preprocessing
- 🧹Logarithmic Transformation: Applied to stabilize variance and mitigate data skewness.
- Infinity Handling: Systematic treatment of values derived from the logarithm of zero.
- Feature Scaling: We use the scale() function to ensure all variables contribute equally to distance calculations, preventing magnitude bias.

### 3. Model Optimization 
🧠Before clustering, we determine the optimal number of groups ($k$) using:

- Elbow Method (WSS): To analyze internal cohesion.
- Silhouette Method: To validate the separation and consistency between clusters.
- Result: The analysis converged on k = 2 as the most natural structure for this dataset.

## 4. Anomaly Identification 
🚩We calculate the distance of each observation to its respective centroid. Different sensitivity thresholds are applied to maximize precision:
- Cluster 1: Threshold of $\mu \pm 4\sigma$ (Strict criteria for high-density groups).
- Cluster 2: Threshold of $\mu \pm 3\sigma$ (Increased sensitivity for secondary groups).

## 🖼️ Interactive 3D Visualization
Using the power of plotly, this project allows for the exploration of the "data cloud" in a three-dimensional space.

🔵 Blue Points: Standard sectoral behavior (Normal).

🔴 Red Points: Detected outliers requiring immediate audit.

This interactive tool facilitates human-in-the-loop validation, confirming that the algorithm successfully isolates extreme cases at the fringes of the multidimensional model.

## 📝 General Conclusions

This exercise demonstrates that outlier detection is significantly more powerful when approached through multivariate analysis. By applying the necessary statistical tools, we can understand not only how much a data point varies in isolation, but how it behaves in relation to its entire environment.

Visualization: Working with a three-variable set allowed us to observe the phenomenon in a 3D plane, which is ideal for human validation.

Scalability: For higher-dimensional detection (more than 3 variables), the next step involves integrating dimensionality reduction techniques (such as PCA or t-SNE) to maintain context without losing interpretability.

- For spanish code: Detección_atípicos_kmeans_aplicado

- For english code: Detección_atípicos_kmeans_aplicado_eng






