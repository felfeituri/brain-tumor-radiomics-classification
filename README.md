# Radiomics-Based Classification of Brain Tumor Subtypes Using Machine Learning

This project develops a radiomics-based machine learning pipeline to classify primary brain tumor subtypes using MRI-derived features.  
The workflow integrates **TCGA** and **REMBRANDT** radiomic data and evaluates multi-class models to distinguish between:

- Glioblastoma (GBM)  
- Oligodendroglioma  
- Astrocytoma  

---

## Overview

The goal of this project is to explore whether radiomic features extracted from brain MRI can help discriminate between major glioma subtypes.

The workflow includes:

- Preparing and harmonizing radiomic feature matrices from multiple cohorts  
- Training a **One-vs-Rest** multi-class classifier  
- Evaluating performance on an external dataset  
- Exploring feature importance to improve interpretability

This work was completed as part of the **HIDS 7009 – Imaging Informatics** course at Georgetown University.

---

## Methods

### 1. Data Preparation

- Imported radiomic features from TCGA and REMBRANDT cohorts  
- Aligned feature sets across datasets (matching column names and removing unmatched features)  
- Filtered to patients with clear subtype labels (GBM, Oligodendroglioma, Astrocytoma)  
- Standardized features (scaling/normalization) prior to model training

### 2. Model Development

- Built a **One-vs-Rest multi-class classification pipeline** using:
  - XGBoost
  - Linear Support Vector Machine (SVM)
  - Gradient Boosting (or similar ensemble models)
- Applied cross-validation and hyperparameter tuning on the training data  
- Evaluated performance using:
  - Accuracy  
  - F1-score  
  - Confusion matrix and per-class metrics  

### 3. External Validation

- Trained models on one cohort and tested on the other (e.g., TCGA → REMBRANDT)  
- Assessed how well models generalize across datasets with different acquisition conditions

### 4. Interpretability

- Computed feature importance scores for each class  
- Highlighted radiomic features that contribute most to discriminating between tumor subtypes  

---

## Repository Structure

```text
brain-tumor-radiomics-classification/
│
├── notebooks/
│   └── Combined_dataset_OneVsRestPipeline.ipynb   # Main analysis notebook
│
├── report/
│   └── Final_Report_Group1.docx                  # Final project report
│
├── presentation                             
│   └── Group 1 Presentation.pptx                  # Final project presentation
└── README.md
```
