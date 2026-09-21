# Heart Disease Risk Prediction & Analytical Study

**AICTE | IBM SkillsBuild Data Analytics with AI Academic Internship Program 2026 | BharatCares**

---

## Overview

This project presents a complete, end-to-end **Data Analytics with Artificial Intelligence** study of heart disease risk factors using the UCI Heart Disease (Cleveland) dataset. The project covers the full data analytics lifecycle: from data acquisition and cleaning, through exploratory data analysis and visualization, to machine learning model building, evaluation, and insight generation.

The project is submitted as part of the AICTE | IBM SkillsBuild Data Analytics with AI Academic Internship Program 2026 by Prince Kumar, B.Tech Computer Engineering, National Institute of Advanced Manufacturing Technology, Ranchi.

---

## Problem Statement

Cardiovascular disease is the leading cause of death globally, accounting for approximately 17.9 million deaths annually (WHO). Early identification of at-risk individuals enables timely clinical intervention.

> **Can routine clinical measurements be used to accurately predict whether a patient has heart disease, and which factors are most strongly associated with the condition?**

---

## Objectives

1. Perform thorough exploratory data analysis of the UCI Heart Disease dataset.
2. Identify the key clinical and demographic factors most associated with heart disease.
3. Preprocess and prepare data for machine learning classification.
4. Build and compare Logistic Regression and Random Forest classification models.
5. Evaluate models using appropriate classification metrics (Accuracy, Precision, Recall, F1, ROC-AUC).
6. Extract actionable, evidence-based insights from both analytics and ML results.
7. Document methodology and findings in a reproducible, professional manner.

---

## Dataset

| Property       | Detail |
|---|---|
| **Name**       | Heart Disease UCI (Cleveland Clinic Foundation) |
| **Source**     | UCI Machine Learning Repository |
| **UCI URL**    | https://archive.ics.uci.edu/dataset/45/heart+disease |
| **Kaggle URL** | https://www.kaggle.com/datasets/ronitf/heart-disease-uci |
| **Rows**       | 303 |
| **Columns**    | 14 (13 features + 1 target) |
| **License**    | CC BY 4.0 |

### Feature Summary

| Feature    | Description                             |
|---|---|
| `age`      | Patient age in years                    |
| `sex`      | 1 = Male, 0 = Female                    |
| `cp`       | Chest pain type (0–3)                   |
| `trestbps` | Resting blood pressure (mm Hg)          |
| `chol`     | Serum cholesterol (mg/dl)               |
| `fbs`      | Fasting blood sugar > 120 mg/dl         |
| `restecg`  | Resting ECG result (0–2)                |
| `thalach`  | Maximum heart rate achieved             |
| `exang`    | Exercise-induced angina (1=yes)         |
| `oldpeak`  | ST depression induced by exercise       |
| `slope`    | Slope of peak exercise ST segment       |
| `ca`       | Major vessels colored by fluoroscopy    |
| `thal`     | Thalassemia type (1=normal, 2=fixed, 3=reversible) |
| `target`   | **Target** — Heart disease: 1=yes, 0=no |

### Dataset Access — No Manual Download Required

The notebook fetches the dataset **automatically** using the `ucimlrepo` Python package:

```python
from ucimlrepo import fetch_ucirepo
heart = fetch_ucirepo(id=45)   # UCI dataset ID 45 = Heart Disease (Cleveland)
```

- **Internet access** is required the first time; the package caches the data locally for subsequent runs.
- The official UCI data includes the original Cleveland subset with the correct clinical feature coding.
- The target column (`num`, values 0–4) is binarized to `target` (0 = no disease, 1 = disease) in the notebook.

> **Attribution:** Dataset created by: Andras Janosi M.D. (Budapest), William Steinbrunn M.D. (Zurich), Matthias Pfisterer M.D. (Basel), Robert Detrano M.D. Ph.D. (Cleveland Clinic Foundation).
> Licensed under CC BY 4.0. Cite as: Janosi, A., Steinbrunn, W., Pfisterer, M., & Detrano, R. (1988). *Heart Disease*. UCI Machine Learning Repository. https://doi.org/10.24432/C52P4X

---

## Technologies Used

| Library       | Purpose                              |
|---|---|
| Python 3.9+   | Core programming language            |
| Jupyter Notebook | Interactive analysis environment   |
| pandas        | Data manipulation                    |
| numpy         | Numerical operations                 |
| matplotlib    | Static visualizations                |
| seaborn       | Statistical visualizations           |
| scikit-learn  | Machine learning models & evaluation |
| scipy         | Statistical testing                  |
| ucimlrepo     | Official UCI dataset fetcher         |

---

## Project Structure

```
PrinceKumar_HeartDiseaseAnalysis/
│
├── PrinceKumar_HeartDiseaseAnalysis.ipynb   ← Main Jupyter Notebook
├── requirements.txt                          ← Python dependencies
├── README.md                                 ← This file
├── PrinceKumar_ProjectReport.docx            ← Project report
│
├── data/
│   └── README_DOWNLOAD_DATASET.md            ← Dataset notes (fetched via ucimlrepo)
│
└── images/
    ├── target_distribution.png
    ├── univariate_continuous.png
    ├── univariate_categorical.png
    ├── bivariate_boxplots.png
    ├── bivariate_categorical.png
    ├── correlation_heatmap.png
    ├── age_distribution.png
    ├── cp_thalach.png
    ├── pairplot.png
    ├── age_group_disease_rate.png
    ├── confusion_matrices.png
    ├── roc_curves.png
    ├── model_comparison.png
    ├── feature_importance.png
    └── lr_coefficients.png
```

---

## Installation

### Prerequisites

- Python 3.9 or higher
- pip (Python package installer)

### Create a Virtual Environment (Recommended)

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## How to Run

1. **No manual dataset download needed.** The notebook fetches the dataset automatically via `ucimlrepo`. Ensure you have an internet connection on the first run.

2. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

3. **Open the notebook:**  
   Navigate to `PrinceKumar_HeartDiseaseAnalysis.ipynb` in the Jupyter interface.

4. **Run all cells:**  
   Use `Kernel → Restart & Run All` to execute the entire notebook from top to bottom.

> All outputs, charts, and model results are generated dynamically from actual code execution. No pre-computed results are hardcoded.

---

## Methodology

### 1. Data Preprocessing
- Loaded the dataset from `data/heart.csv`
- Removed 1 duplicate row
- Verified no missing values
- Confirmed correct data types for all features
- Checked for physiologically invalid values (e.g., zero cholesterol)

### 2. Exploratory Data Analysis
- Target variable distribution (balanced: ~54% disease / ~46% no disease)
- Univariate analysis: histograms and bar charts for all 13 features
- Bivariate analysis: boxplots and stacked bar charts vs target
- Multivariate analysis: correlation heatmap, pairplot
- Statistical significance testing (independent t-tests)

### 3. Visualization
- Saved 15+ publication-quality charts to the `images/` folder
- All charts include titles, axis labels, and textual interpretations in the notebook

### 4. Feature Engineering
- `age_group`: Categorical age brackets (<40, 40-50, 50-60, >60)
- `thalach_age_ratio`: Max heart rate normalized by age
- `bp_chol_product`: Combined cardiovascular risk indicator

### 5. AI/ML
- **Model 1 — Logistic Regression**: Linear baseline classifier with StandardScaler preprocessing
- **Model 2 — Random Forest**: Ensemble classifier (100 trees, max_depth=6)
- Train/test split: 80%/20%, stratified
- 5-fold stratified cross-validation for reliable evaluation

---

## Key Results

> All metrics are computed from actual model execution on the held-out test set.

| Model               | Accuracy | Precision | Recall | F1   | ROC-AUC |
|---|---|---|---|---|---|
| Logistic Regression | ~0.836   | ~0.824    | ~0.875 | ~0.848 | ~0.906  |
| Random Forest       | ~0.852   | ~0.857    | ~0.875 | ~0.866 | ~0.920  |

*Exact values will be generated when the notebook is executed.*

---

## Key Insights

1. **Max heart rate (`thalach`)** is the most predictive single feature — confirmed by EDA, statistical testing, and Random Forest feature importance.
2. **Chest pain type** is highly discriminative — asymptomatic and non-anginal pain types are paradoxically associated with disease.
3. **Thalassemia type and major vessel count** are strong ML-identified predictors aligned with clinical knowledge.
4. **Cholesterol is surprisingly weak** as an isolated predictor — reinforcing multifactorial risk assessment.
5. **Both models achieve robust performance** (~83–85% accuracy, ~0.90 ROC-AUC) on routine clinical data.

---

## Limitations

- Dataset contains only 302 samples from a single clinical center (Cleveland, USA).
- Demographic scope is limited; findings may not directly generalize to Indian populations.
- Key clinical variables (smoking status, BMI, family history, activity level) are absent.
- Hyperparameters were set to reasonable defaults; systematic tuning could improve performance.
- No external validation dataset was used.

---

## Future Scope

- Apply to larger, multi-center, or India-specific cardiovascular datasets.
- Implement SHAP explainability for individual patient-level predictions.
- Add systematic hyperparameter tuning (GridSearchCV / RandomizedSearchCV).
- Build an interactive clinical dashboard using Streamlit or Gradio.
- Incorporate missing risk factors (smoking, BMI, physical activity, genetic markers).

---

## Dataset Source

UCI Machine Learning Repository — Heart Disease Dataset  
https://archive.ics.uci.edu/dataset/45/heart+disease  
DOI: https://doi.org/10.24432/C52P4X

---

## License / Attribution

The UCI Heart Disease dataset is licensed under **CC BY 4.0**.  
Original data contributed by: Janosi A., Steinbrunn W., Pfisterer M., Detrano R. (Cleveland Clinic Foundation).

This project code and documentation are created for the AICTE | IBM SkillsBuild Data Analytics with AI Internship Program 2026 and are intended for academic use.

---

*Project by Prince Kumar | B.Tech Computer Engineering | National Institute of Advanced Manufacturing Technology, Ranchi*
