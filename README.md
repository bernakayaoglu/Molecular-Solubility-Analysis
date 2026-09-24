# Molecular Solubility Analysis

A cheminformatics and machine learning project for predicting aqueous molecular solubility from molecular properties and chemical structure.

## Project Overview

This project investigates the relationship between molecular structure, physicochemical properties, and aqueous solubility using the Delaney (ESOL) dataset.

The analysis combines exploratory data analysis, RDKit molecular descriptors, Morgan fingerprints, and machine learning models. Different molecular representations are compared to evaluate their effect on solubility prediction.

## Methods

- Exploratory Data Analysis (EDA)
- Physicochemical descriptor analysis
- RDKit molecular descriptor generation
- Morgan fingerprint generation
- Linear Regression
- Random Forest Regression
- Hyperparameter tuning
- Cross-validation
- Residual and error analysis
- Molecular similarity analysis using Tanimoto similarity

## Model Performance

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 0.90 | 1.21 | 0.69 |
| ESOL | 0.71 | 0.96 | 0.81 |
| Random Forest – Basic Descriptors | 0.60 | 0.91 | 0.83 |
| Random Forest – RDKit Descriptors | 0.55 | 0.80 | 0.86 |
| Random Forest – Morgan Fingerprints | 0.89 | 1.17 | 0.71 |
| Random Forest – Combined | **0.54** | **0.79** | **0.87** |

The combined model using RDKit descriptors and Morgan fingerprints achieved the highest test performance among the evaluated models.

## Key Findings

Molecular descriptors provided strong predictive information for aqueous solubility. LogP was particularly informative, showing a strong negative relationship with measured solubility.

Morgan fingerprints alone performed worse than descriptor-based models, while combining fingerprints with physicochemical descriptors produced a small additional improvement.

Error and molecular similarity analyses showed that some of the largest prediction errors occurred for molecules with relatively low structural similarity to the training data. However, the overall relationship between structural similarity and prediction error was weak (r = -0.20), indicating that chemical-space coverage alone does not explain all prediction errors.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- RDKit
- Jupyter Notebook

## Dataset

Delaney ESOL dataset containing measured aqueous solubility and molecular properties for 1,128 compounds.

## Project Structure

```text
MolecularSolubility/
├── data/
│   └── delaney-processed.csv
├── Molecular_Solubility_Analysis.ipynb
├── README.md
├── requirements.txt
└── .gitignore