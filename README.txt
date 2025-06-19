# IceCube Event Classification with Machine Learning

This project applies Machine Learning techniques to classify simulated events from the IceCube experiment, distinguishing neutrino signals from atmospheric muon background.

## 📍 Overview

- **Experiment**: IceCube is a neutrino detector located at the South Pole that uses optical sensors to detect Cherenkov light emitted by charged particles produced in neutrino interactions.
- **Goal**: To classify events as signal (neutrinos) or background (muons) using supervised Machine Learning algorithms.
- **Data**: Three simulated datasets provided — signal, background (for training), and test (for prediction).

##⚙️ Workflow

### 1. Data Preparation
- Removed non-shared columns, event IDs, and Monte Carlo weights.
- Dropped rows with NaN or infinite values.
- Merged signal and background datasets to build the training set.

### 2. Feature Selection
- Used **mRMR (Minimum Redundancy Maximum Relevance)** to select 12 key features out of 187, reducing dimensionality and redundancy while preserving relevant information.

### 3. Model Training & Evaluation
The following classifiers were implemented:
- **Random Forest (RF)**
- **Naïve Bayes (NB)**
- **k-Nearest Neighbors (kNN)**

Evaluation metrics:
- Accuracy, Precision, Recall, fβ-score (with β = 0.1)
- ROC Curves and Area Under the Curve (AROC)
- 10-fold Cross-Validation to estimate statistical uncertainty

## 📊 Results

| Model | Accuracy | Precision | Recall | AROC | fβ-score |
|-------|----------|-----------|--------|------|----------|
| RF    | 0.9360 ± 0.0015 | 0.9521 ± 0.0020 | 0.9175 ± 0.0024 | **0.9810 ± 0.0009** | 0.9517 ± 0.0020 |
| NB    | 0.8433 ± 0.0018 | 0.8900 ± 0.0041 | 0.7816 ± 0.0034 | 0.9248 ± 0.0016 | 0.8888 ± 0.0041 |
| kNN   | 0.8696 ± 0.0027 | 0.8681 ± 0.0048 | 0.8700 ± 0.0023 | 0.9164 ± 0.0018 | 0.8681 ± 0.0047 |

## ✅ Conclusion

The **Random Forest** classifier outperformed the others, achieving the highest AROC, fβ-score, and overall accuracy. It was selected as the final model for test dataset predictions.

---

**Authors**:  
- Edgar Eduardo Mata Mendoza  
- Josue Salvador Elizalde Palacios  

**Date**: June 2024  
**Institution**: Technical University of Dortmund
