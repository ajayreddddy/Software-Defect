# Software Defect Prediction Using Machine Learning

## Project Overview

This project predicts software defects using Machine Learning and Deep Learning. It analyzes historical software metrics and classifies whether a software module is **defective** or **non-defective** before deployment — helping teams prioritize testing and reduce maintenance costs.

> **Environment:** This project is designed to run as a **Jupyter Notebook (`.ipynb`)** — locally or on Kaggle.

---

## Problem Statement

Traditional manual testing is time-consuming, costly, error-prone, and hard to scale. This project automates defect detection using ML models trained on historical software metrics.

---

## Objectives

- Analyze a software defect dataset
- Perform Exploratory Data Analysis (EDA)
- Preprocess, scale, and split the data
- Train and compare multiple ML/DL models
- Identify key software metrics contributing to defects

---

## Dataset

**Source:** [Software Defect Prediction Dataset — Kaggle](https://www.kaggle.com/datasets/mirzayasirabdullah07/software-defect-prediction-dataset)

| Property | Details |
|----------|---------|
| Total Records | 60,000 software modules |
| Total Features | 23 |
| Target Variable | `0` = Non-defective, `1` = Defective |

### Key Features

`lines_of_code`, `cyclomatic_complexity`, `num_functions`, `code_churn`, `test_coverage`, `duplication_percentage`, `static_analysis_warnings`, `coupling_between_objects`, `past_defects`, `performance_issues`, `security_vulnerabilities`

---

## Technologies Used

| Category | Libraries |
|----------|-----------|
| Data Processing | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn` |
| Machine Learning | `scikit-learn`, `xgboost` |
| Deep Learning | `tensorflow`, `keras` |

---

## How to Run — Jupyter Notebook

### Option A: Run on Kaggle (Recommended — no setup needed)

1. Go to the dataset page: [Kaggle Dataset Link](https://www.kaggle.com/datasets/mirzayasirabdullah07/software-defect-prediction-dataset)
2. Click **"New Notebook"** on the dataset page — this auto-mounts the dataset
3. Upload `software-prediction.ipynb` via **File → Import Notebook**
4. The dataset path in the notebook is already set correctly:
   ```python
   file_path = "/kaggle/input/datasets/mirzayasirabdullah07/software-defect-prediction-dataset/software_defect_prediction_dataset.csv"
   ```
5. Click **Run All** (or Shift+Enter through each cell)

---

### Option B: Run Locally in Jupyter

#### Step 1: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost tensorflow jupyter
```

#### Step 2: Download the Dataset

Download `software_defect_prediction_dataset.csv` from [Kaggle](https://www.kaggle.com/datasets/mirzayasirabdullah07/software-defect-prediction-dataset) and place it in your project folder.

#### Step 3: Update the Dataset Path

Open `software-prediction.ipynb` and change the file path in **Cell 2**:

```python
# Change this line:
file_path = "/kaggle/input/datasets/mirzayasirabdullah07/software-defect-prediction-dataset/software_defect_prediction_dataset.csv"

# To your local path, e.g.:
file_path = "software_defect_prediction_dataset.csv"
```

#### Step 4: Launch Jupyter and Run

```bash
jupyter notebook
```

Open `software-prediction.ipynb` and run all cells in order (**Cell → Run All**).

---

## Project Workflow

```
Dataset Loading
      ↓
Exploratory Data Analysis (EDA)
      ↓
Data Preprocessing & Scaling
      ↓
Train-Test Split (80/20)
      ↓
Model Training (4 models)
      ↓
Model Evaluation
      ↓
Feature Importance Analysis
```

---

## Models Implemented

### 1. Random Forest Classifier
Uses multiple decision trees. Handles complex relationships and reduces overfitting.

### 2. Gradient Boosting Classifier
Sequentially corrects previous errors. High accuracy on classification tasks.

### 3. XGBoost Classifier
Optimized boosting with regularization. Fast and highly accurate.

### 4. Deep Neural Network (TensorFlow/Keras)

```
Input Layer → Dense(64, ReLU) → Dense(32, ReLU) → Output(1, Sigmoid)
```

---

## Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Random Forest | **100%** | 1.0 | 1.0 | 1.0 |
| Gradient Boosting | **100%** | 1.0 | 1.0 | 1.0 |
| XGBoost | 99.98% | — | — | — |
| Neural Network | 99.43% | — | — | — |

> ⚠️ Near-perfect accuracy may indicate overfitting or synthetic dataset patterns. Validation on real-world data is recommended.

### Top Features by Importance (Random Forest)
1. `past_defects`
2. `static_analysis_warnings`
3. `cyclomatic_complexity`
4. `test_coverage`

---

## Outputs Generated

- Defect distribution bar chart
- Correlation heatmap
- Boxplots (lines of code, complexity, test coverage)
- Confusion matrices for all models
- ROC curves (AUC ≈ 1.0 for all models)
- Feature importance chart

---

## Challenges

- **Class imbalance** — dataset has significantly more defective than non-defective modules
- **Near-perfect accuracy** — possible overfitting or artificial dataset patterns; real-world validation needed

---

## Future Improvements

- Use real-world industrial datasets (e.g., NASA, PROMISE)
- Apply SMOTE for class imbalance handling
- Hyperparameter tuning with GridSearchCV
- Add cross-validation
- Deploy as a web app using Streamlit or Flask

---

## Project Structure

```
Software Defect Prediction Using Machine Learning/
│
├── software-prediction.ipynb       ← Main notebook (run this)
├── Software Defect Prediction Using Machine Learning.pptx
└── README.md
```

> **Note:** Download the dataset from Kaggle separately — it is not included in this repository.

---

## Conclusion

This project demonstrates that machine learning can reliably predict software defects from code metrics. Random Forest and Gradient Boosting achieved the best results, while the Neural Network also performed strongly. The most influential predictors were historical defects, static analysis warnings, cyclomatic complexity, and test coverage.

---

*This project is for educational and research purposes.*
