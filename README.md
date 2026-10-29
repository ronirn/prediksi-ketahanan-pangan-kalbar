
<div align="center">

# Food Security Index Prediction

### A Machine Learning Approach to Regional Food Security Assessment

**West Kalimantan, Indonesia · 2021–2025**

A web-based research application for estimating and exploring the
Food Security Index using Multilayer Perceptron neural networks,
official regional statistics, and interactive geospatial visualizations.

<br>

**Python** &nbsp;·&nbsp; **Flask** &nbsp;·&nbsp; **Scikit-learn** &nbsp;·&nbsp; **Tailwind CSS** &nbsp;·&nbsp; **Chart.js** &nbsp;·&nbsp; **Leaflet**

<br>

[Overview](#overview) &nbsp;·&nbsp;
[Application](#application-showcase) &nbsp;·&nbsp;
[Methodology](#methodology) &nbsp;·&nbsp;
[Results](#experimental-results) &nbsp;·&nbsp;
[Technology](#technology-stack)

</div>

---

## Overview

Food security is a fundamental dimension of regional development,
reflecting the availability, accessibility, and utilization of food
resources. Understanding its spatial and temporal characteristics
is essential for evidence-based analysis.

This project explores the application of **Multilayer Perceptron (MLP)**
neural networks to estimate the Food Security Index (FSI), locally
known as *Indeks Ketahanan Pangan* (IKP), across districts and
municipalities in West Kalimantan Province, Indonesia.

The research integrates official data from **Statistics Indonesia (BPS)**
and the **National Food Agency (BAPANAS)** into a machine learning
workflow, supported by a Flask-based web application for interactive
exploration and model evaluation.

### Project at a Glance

| | |
|:---|:---|
| **Study Area** | West Kalimantan, Indonesia |
| **Geographic Coverage** | 14 districts and municipalities |
| **Observation Period** | 2021–2025 |
| **Dataset Size** | 70 observations |
| **Input Features** | 6 socioeconomic and food-related indicators |
| **Prediction Target** | Food Security Index (FSI / IKP) |
| **Primary Method** | Multilayer Perceptron |
| **Selected MLP Configuration** | MLP Ensemble Log |
| **Validation Strategy** | Rolling-origin historical validation |
| **Data Providers** | BPS and BAPANAS |

---

## Application Showcase

The research is supported by a responsive web application designed
to make regional food security data and model outputs more accessible.

The interface is organized into five integrated modules.

### 01 / Dashboard

**Regional food security at a glance.**

The dashboard provides an overview of Food Security Index conditions
across West Kalimantan. It combines regional statistics, historical
trends, and an interactive geographic map into a single interface.

Key capabilities include regional filtering, year selection,
summary indicators, and geographic exploration.

<p align="center">
  <a href="Dokumentasi/dashboard.png">
    <img
      src="Dokumentasi/dashboard.png"
      alt="Dashboard — Regional Food Security Overview"
      width="100%"
    >
  </a>
</p>

<p align="center"><sub>Figure 01 — Regional Food Security Dashboard</sub></p>

<br>

### 02 / Dataset Explorer

**Explore the data behind the research.**

The dataset explorer presents historical observations and research
variables in a structured, searchable interface.

Users can examine socioeconomic and food-related indicators,
filter observations by region and year, sort records,
and export available data.

<p align="center">
  <a href="Dokumentasi/dataset.png">
    <img
      src="Dokumentasi/dataset.png"
      alt="Dataset Explorer — Historical Food Security Data"
      width="100%"
    >
  </a>
</p>

<p align="center"><sub>Figure 02 — Historical Dataset Explorer</sub></p>

<br>

### 03 / Food Security Estimation

**From regional indicators to model-based estimates.**

The prediction interface integrates the trained MLP Ensemble Log
model into a structured input workflow.

Users provide six socioeconomic and food-related indicators
to generate an estimated Food Security Index value, accompanied
by an indicative interpretation.

The application includes input validation and temporary
prediction history.

<p align="center">
  <a href="Dokumentasi/prediksi.png">
    <img
      src="Dokumentasi/prediksi.png"
      alt="Prediction Interface — MLP-Based FSI Estimation"
      width="100%"
    >
  </a>
</p>

<p align="center"><sub>Figure 03 — Food Security Index Estimation Interface</sub></p>

<br>

### 04 / Data Visualization

**Understanding patterns across space and time.**

The visualization module enables interactive analysis
of regional Food Security Index values through:

- Historical trend analysis
- Cross-regional comparisons
- Score distribution visualization
- Interactive geographic mapping

These visualizations support descriptive exploration
of differences between districts and municipalities.

<p align="center">
  <a href="Dokumentasi/visual.png">
    <img
      src="Dokumentasi/visual.png"
      alt="Visualization — Regional Trends and Geographic Patterns"
      width="100%"
    >
  </a>
</p>

<p align="center"><sub>Figure 04 — Interactive Data Visualization</sub></p>

<br>

### 05 / Model Evaluation

**Transparent assessment of predictive performance.**

The evaluation dashboard presents experimental results
using three regression metrics:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Coefficient of Determination (R²)

It supports comparisons between MLP, Naïve, and
Linear Regression across historical validation periods.

<p align="center">
  <a href="Dokumentasi/evaluasi.png">
    <img
      src="Dokumentasi/evaluasi.png"
      alt="Model Evaluation — Performance Metrics and Comparisons"
      width="100%"
    >
  </a>
</p>

<p align="center"><sub>Figure 05 — Model Evaluation Dashboard</sub></p>

---

## Methodology

### Research Design

The study follows a structured machine learning workflow,
from data integration to model evaluation and application development.

**Data Collection → Integration → Preprocessing → Model Development → Temporal Validation → Web Implementation**

### Data and Features

The research dataset covers 14 administrative regions
over five annual observation periods, resulting in
70 region-year observations.

Six indicators are used as model inputs:

| Feature | Description |
|:---|:---|
| X1 | Poverty rate |
| X2 | Monthly per capita expenditure |
| X3 | Open unemployment rate |
| X4 | Population density |
| X5 | Paddy production |
| X6 | Prevalence of Undernourishment (PoU) |

The target variable is the **Food Security Index (IKP)**
published by BAPANAS.

### Model Development

Several MLP configurations were investigated to assess
the influence of preprocessing and model configuration
on prediction performance.

The selected **MLP Ensemble Log** approach combines
five independently initialized MLP networks.

Selected input variables undergo logarithmic
transformation followed by feature standardization.
The ensemble prediction is obtained by averaging
the outputs of the individual models.

### Validation Strategy

To preserve chronological ordering, the study
employs **rolling-origin validation** for the
historical 2022 and 2023 evaluation periods.

A Naïve baseline and a six-feature Linear Regression
model are included for comparative analysis.

---

## Experimental Results

### Historical Validation Performance

The following table summarizes performance during
the 2022–2023 historical validation periods.

| Model | MAE ↓ | RMSE ↓ | R² ↑ |
|:---|---:|---:|---:|
| **MLP Ensemble Log** | 3.229 | 3.714 | 0.609 |
| Naïve Baseline | **2.101** | **2.866** | **0.755** |
| Linear Regression (6 Features) | 4.648 | 5.579 | 0.123 |

*Lower MAE and RMSE indicate smaller prediction errors;
higher R² indicates better explanatory performance.*

### Key Findings

**01 — MLP configuration selection**

MLP Ensemble Log achieved the strongest results
among the evaluated MLP configurations.

**02 — Baseline comparison**

The Naïve baseline outperformed the selected MLP
during historical validation. However, the two
approaches use different information sets:
Naïve relies on the previous year's observed index,
whereas MLP estimates the index from six contemporaneous indicators.

**03 — Temporal generalization**

Performance deteriorated when the historical model
was assessed against the 2024–2025 index values.
This finding must be interpreted in the context
of changes in the official index methodology.

### Limitations

The study has several important limitations.

First, the available dataset contains only 70 annual
region-level observations, limiting the amount of
information available for model training and evaluation.

Second, the official Food Security Index methodology
changed in 2024. The 2021–2023 historical series and
the 2024–2025 12-indicator series are not directly
comparable without methodological consideration.

Third, the model is designed to estimate IKP using
indicators from the **same observation year**.
It does not perform independent future-year forecasting.

Accordingly, the results should be interpreted as
research-based estimates rather than operational
forecasts or official BAPANAS index values.

---

## Technology Stack

| Layer | Technologies |
|:---|:---|
| Application Framework | Flask, Python |
| Machine Learning | Scikit-learn, MLPRegressor |
| Data Processing | Pandas, NumPy |
| Frontend | HTML, Tailwind CSS, JavaScript |
| Charts | Chart.js |
| Geospatial Visualization | Leaflet, GeoJSON |
| Model Persistence | Joblib |

---

## Repository Scope

This repository serves as a **public-facing research and
software development portfolio**.

It includes application screenshots, project documentation,
methodological information, and summarized experimental results.

The application source code, trained models, and research
datasets are maintained separately and are not distributed
through this repository.

---

## Author

**Roni, S.Kom.**

Machine Learning · Applied Data Science · Web Development

West Kalimantan, Indonesia

---

<div align="center">

<sub>Food Security Index Prediction · West Kalimantan, Indonesia</sub>

<br>

<sub>Research & Software Development Portfolio — 2026</sub>

</div>
