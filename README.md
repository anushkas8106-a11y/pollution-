## Global Pollution Analysis and Energy Recovery Prediction

# Project Overview

This project aims to analyze global pollution data across various countries and predict how pollution levels can impact energy recovery. Using clustering techniques (K‑Means and Hierarchical Clustering) and a neural network model, the system identifies pollution patterns, groups countries with similar environmental characteristics, and predicts the amount of energy recovered from waste and pollution sources. The insights derived can help policymakers design targeted environmental and energy strategies.

# Objectives

Analyze pollution indices (air, water, soil) and their relationship with energy recovery.

Cluster countries based on pollution levels and energy recovery metrics.

Build a neural network to predict energy recovery (in GWh) from pollution and economic features.

Compare clustering results with predictive model performance.

Provide actionable insights for reducing pollution and improving energy recovery.

# Methodology

## Phase 1: Data Preprocessing and Feature Engineering

Data Processing

Loaded dataset Global_Pollution_Analysis.csv (200 rows, 13 columns).

Handled missing values – no missing data detected.

Encoded categorical variable Country using Label Encoding.

Normalized numerical features (pollution indices, energy metrics) for clustering and neural network input.

Feature Engineering
Created Total_Pollution_Index as the average of air, water, and soil pollution indices.

Explored yearly pollution trends and their impact on energy recovery.

## Phase 2: Clustering Analysis

# K-Means Clustering

# Objective

Group countries based on pollution levels and energy recovery to identify similar environmental and energy profiles.

# Implementation

Applied K‑Means on scaled features (air, water, soil pollution, energy recovered, CO₂ emissions, renewable energy percentage, energy consumption per capita, total pollution index).

Used Elbow Method to determine optimal number of clusters → 3 clusters.

Results
Clusters were characterized as:

Cluster	Profile
0	High pollution, moderate energy recovery
1	Moderate pollution, moderate recovery
2	Lower pollution, moderate–high recovery
Visualization
PCA projection showed clear separation between clusters.

# Hierarchical Clustering

# Objective

Understand hierarchical relationships among pollution and energy features.

# Implementation

Applied Agglomerative Clustering with Ward linkage.

Visualized dendrogram to determine number of clusters.

Results
Dendrogram confirmed 3 clusters, with high agreement with K‑Means (contingency table showed consistency). Hierarchical clustering revealed nested similarities, e.g., some high‑pollution countries grouped separately based on renewable energy usage.

Clustering Insights

Countries with high pollution often have lower energy recovery, indicating inefficiency.

Moderate‑pollution clusters show a balance between environmental impact and recovery.

Lower‑pollution countries tend to have higher renewable energy shares and better recovery outcomes.

## Phase 3: Neural Network Prediction

Model Used

Feedforward Neural Network built with Keras/TensorFlow.

Input Features

Air Pollution Index

CO₂ Emissions (MT)

Industrial Waste (tons)

Renewable Energy (%)

Energy Consumption per Capita (MWh)

Population (millions)

GDP per Capita (USD)


Output
Energy Recovered (GWh) – a continuous variable.

Evaluation Metrics

R², Mean Squared Error (MSE), Mean Absolute Error (MAE).

Model Comparison
Model	R² (Test)	MSE (Test)	MAE (Test)

Linear Regression	-0.07	-	-

Simple Neural Network	-0.162	28098.2	149.9

Tuned Neural Network	-0.166	-	-

Key Finding

Neural networks achieved slightly better R² than linear regression, but both performed poorly (negative R²). This suggests that the current features are not sufficient to accurately predict energy recovery; more sophisticated feature engineering or additional data (e.g., policy factors, infrastructure) is needed.

## Phase 4: Reporting and Insights

Model Comparison Insights

Clustering (both K‑Means and Hierarchical) successfully identified meaningful groups of countries with similar pollution‑energy profiles.

Neural network predictions were not accurate with the given features; future work should incorporate more relevant predictors (e.g., waste‑to‑energy policies, industrial efficiency) or use time‑series models.

Actionable Insights

High‑pollution, low‑recovery countries (Cluster 0) should prioritize investment in waste‑to‑energy infrastructure and stricter emission controls.

Moderate clusters (1 and 2) can serve as benchmarks; policies from low‑pollution countries (e.g., high renewable energy adoption) can be adapted.

Clustering can be updated annually to track progress and inform policy adjustments.

Limitations

Dataset is limited to 200 rows, which may not capture all global variations.

Neural network performance was poor due to insufficient predictive features.

External factors (e.g., national policies, technological adoption) were not included.

Future Scope

Incorporate additional features such as environmental policy indices, urban population density, and industrial composition.

Experiment with other models: XGBoost, Random Forests, or LSTM for time‑series forecasting.

Develop a real‑time dashboard for monitoring pollution and energy recovery trends.

Extend analysis with more granular data (e.g., city‑level) for deeper insights.

# Conclusion

This project demonstrates how clustering techniques can reveal natural groupings of countries based on pollution and energy recovery. While the neural network predictions were limited, the clustering insights provide actionable guidance for policymakers. Combining clustering with predictive models can offer a comprehensive framework for sustainable environmental management.

