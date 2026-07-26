## Cancer-Associated Missense Variant Pathogenicity Prediction Using TensorFlow

---

## Project Overview

This project investigates whether biologically informed feature engineering can improve the prediction of pathogenic cancer-associated missense variants using TensorFlow-based neural networks.

Beginning with a simple baseline classifier, the project incrementally develops increasingly sophisticated models by introducing new preprocessing strategies, biologically meaningful features, neural network architectures, and evaluation techniques. 

---

## Objectives

- Develop and evaluate TensorFlow-based neural network models for missense variant pathogenicity prediction.
- Investigate how biologically informed features improve neural network performance.
- Optimize neural network architectures and feature representations to improve predictive performance.
- Assess model performance using robust evaluation metrics and cross-validation techniques.

---

## Dataset

This project uses clinically annotated missense variants obtained from the **ClinVar** database for multiple cancer-associated genes.

Detailed information about dataset composition is available in the **ProjectConclusions.md** document.

---

## Techniques Explored

Throughout the project, several machine learning and bioinformatics techniques were implemented, including:

- Random Forest classification
- TensorFlow/Keras neural networks
- Raw mutation position features 
- One-hot encoding
- Amino acid physicochemical properties
- BLOSUM62 substitution scores
- Functional protein domain and structural region features derived from mutation position
- Class weighting for imbalanced datasets
- ROC curve analysis
- Threshold optimization using Youden's J statistic
- Repeated stratified train-test evaluation
- Repeated Stratified K-Fold cross-validation
- Confidence interval estimation

---

## Repository Structure

```
Notebooks/
│
├── Notebook 1 - Baseline Random Forest
├── Notebook 2 - Neural Network
├── Notebook 3 - Gene Expansion
├── Notebook 4 - ROC Evaluation
├── Notebook 5 - Dataset Refinement
├── Notebook 6 - BLOSUM62 Features
├── Notebook 7 - Advanced Feature Engineering
├── Notebook 8 - Repeated Stratified K-Folds
└── Notebook 9 - Final Analysis
```

---

## Notebook Summary

### Notebook 1 — Baseline Random Forest
- Develops the initial machine learning baseline using amino acid substitutions and raw mutation position features

### Notebook 2 — Neural Network
- Introduces TensorFlow neural networks and amino acid physicochemical properties.

### Notebook 3 — Dataset Expansion
- Expands the dataset to additional genes while introducing one-hot encoded mutation features.

### Notebook 4 — Model Evaluation
- Introduces ROC-AUC analysis to complement accuracy-based evaluation.

### Notebook 5 — Dataset Refinement
- Removes genes that reduced model quality and introduces class weighting to address class imbalance.

### Notebook 6 — Evolutionary Feature Engineering
- Adds BLOSUM62 substitution scores to capture evolutionary similarity between amino acid substitutions.

### Notebook 7 — Advanced Feature Engineering
- Introduces biologically informed features derived from protein structural regions and known mutational hotspot regions. ROC-based threshold optimization using Youden's J statistic is also implemented to improve classification decisions.

### Notebook 8 — Repeated Stratified K-Folds
- Implements repeated stratified K-fold cross-validation to provide a more robust and reliable assessment of model performance while preserving the benign-to-pathogenic class distribution across each fold.

### Notebook 9 — Final Analysis
- Integrates the most effective preprocessing methods, biologically informed feature engineering strategies, neural network architecture, and evaluation techniques into the final TensorFlow implementation.

---

## Quick Start

If you'd like to understand the project without reviewing every notebook, begin with:

**Notebooks/Notebook_9_Final_Analysis.ipynb**

This notebook presents the complete machine learning pipeline, including the final preprocessing workflow, feature engineering approach, neural network architecture, and evaluation methodology. It serves as a concise overview of how the techniques developed throughout the previous notebooks were combined into the final model.

The earlier notebooks document the project's iterative development, with each notebook introducing and evaluating a specific improvement to the model.

For a concise summary of the project's objectives, methodology, performance, biological significance, limitations, and overall conclusions, see the **ProjectConclusions.md** document. 

---

## Installation

Developed using **Python 3.11.4**

Clone the repository:

```bash
git clone https://github.com/tristang42/Cancer-Variant-Pathogenicity-Classifier.git

cd Cancer-Variant-Pathogenicity-Classifier

python -m venv test_env

# Windows PowerShell
.\test_env\Scripts\Activate.ps1

python -m pip install -r requirements.txt
```
---

## Running Notebooks 

Launch Jupyter Notebook:

```bash
jupyter notebook
```
---

## License

This project is provided for educational and research purposes.

--- 
