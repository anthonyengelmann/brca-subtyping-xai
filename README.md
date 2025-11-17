# BRCA-SubtypeXAI: Explainable Deep Learning for Breast Cancer Subtyping

![Status](https://img.shields.io/badge/Status-Work%20in%20Progress-orange.svg)

This project is a "Work in Progress". The current focus is on data acquisition, preprocessing, and exploratory data analysis (EDA).

## 1. Project Overview & Motivation

Molecular subtyping of breast cancer (e.g., Luminal A/B, HER2-positive, Basal-like) is a critical step for prognosis and personalized treatment selection. While established methods like IHC or commercial assays (e.g., PAM50) provide valuable classifications, they often operate as rigid "black boxes," can be costly, or are technically demanding.

This project aims to build an **open-source, lightweight, and explainable machine learning model** that accurately classifies breast cancer subtypes based on RNA-Seq gene expression data (from the TCGA-BRCA dataset).

The primary goal is not just to replicate existing tools but to provide **biologically interpretable insights** into the model's decisions. By integrating **Explainable AI (XAI)** methods such as **SHAP**, the model serves as a transparent tool for research, education, and hypothesis generation.

## 2. Project Phases & Current Status

The project is structured into five methodological phases.

**Current Status: Phase 2 (Data Acquisition & Preprocessing)**

* **Phase 0: Background Research:** *(Completed)* - Definition of biomedical relevance and problem statement (see `00_biomedial_background.ipynb`).
* **Phase 1: Project Definition:** *(Completed)* - Establishment of goals, methodology, and tools (see `01_project_description.ipynb`).
* **Phase 2: Data Acquisition & Preprocessing:** *(In Progress)* - Documented in `02_data_acquisition_and_exploration.ipynb`.
    * TCGA-BRCA RNA-Seq data (FPKM) acquired from UCSC Xena Hub.
    * PAM50 subtype labels acquired via `TCGAbiolinks`.
    * Data merging, ID alignment, and matrix transposition completed.
    * Noise reduction: Removal of "Normal-like" samples to focus on 4 main subtypes.
    * Label encoding applied (e.g., LumA -> 0, LumB -> 1).
    * Initial Feature Filtering (VarianceThreshold > 0.01) performed (Reduced from ~60k to ~37k features).
    * Exploratory Data Analysis (EDA): Class balance investigation.
* **Phase 3: Model Development:** *(Next Step)*
* **Phase 4: Model Interpretation:** *(Planned)*
* **Phase 5: Documentation:** *(Planned)*

## 3. Methodology & Tools

The core of this project is a pipeline transforming raw gene expression data into an interpretable classification model.

1.  **Data Source:** TCGA-BRCA (UCSC Xena & TCGAbiolinks)
2.  **Preprocessing:** Normalization, Noise Filtering (Variance Threshold)
3.  **Feature Selection:** (Planned) e.g., ANOVA, Model-based (Random Forest)
4.  **Modeling:** (Planned) XGBoost, scikit-learn
5.  **Evaluation:** (Planned) K-Fold Cross-Validation, ROC-AUC, Confusion Matrix
6.  **Explainability:** **SHAP**

**Technologies Used:**
* Python (Jupyter Notebooks)
* Pandas & NumPy
* Matplotlib & Seaborn
* Scikit-learn, XGBoost
* SHAP
* Git & GitHub

## 4. Repository Structure

* `/00_biomedial_background.ipynb`: Defines the medical problem and scientific motivation.
* `/01_project_description.ipynb`: Defines project goals, methodology, and phases.
* `/02_data_acquisition_and_exploration.ipynb`: Loads, cleans, and explores raw data.