# Lung Cancer Risk Prediction

This repository contains a research-style machine learning workflow for lung cancer risk analysis using a single end-to-end notebook.

The project focuses on more than standard classification. It also includes fairness evaluation, explainability, causal analysis, survival analysis, and multi-task modeling.

## Dataset

Source: https://www.kaggle.com/datasets/ankushpanday1/lung-cancer-risk-and-prediction-dataset/data

Primary data file in this repository:

- `data/lung_cancer_prediction.csv`

## Project Structure

```text
Lung-Cancer-Risk-Prediction/
├── lung_cancer_research.ipynb
├── requirements.txt
├── README.md
├── LICENSE
├── data/
│   ├── lung_cancer_prediction.csv
│   └── fig*.png
└── catboost_info/
```

## What the Notebook Covers

The notebook is organized into a full pipeline:

1. Library imports and configuration
2. Data loading and exploration
3. Exploratory data analysis (EDA)
4. Data cleaning and preprocessing
5. Feature engineering
6. Feature selection and encoding
7. Model benchmarking
8. Hyperparameter optimization (Optuna)
9. Explainability (SHAP and permutation importance)
10. Fairness analysis
11. Causal graph and counterfactual analysis
12. Survival analysis (Kaplan-Meier and Cox)
13. Healthcare disparity analysis
14. Multi-task learning experiments
15. Statistical significance testing (McNemar's test)
16. Results summary and discussion

## Setup

### 1. Create a virtual environment (recommended)

Windows PowerShell:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### 2. Install dependencies

```powershell
pip install -r requirements.txt
```

### 3. Open and run the notebook

```powershell
jupyter notebook lung_cancer_research.ipynb
```

In VS Code, use **Restart Kernel and Run All** for a clean execution.

## Runtime Notes

- Some sections are computationally heavy (especially Optuna, SHAP, and fairness constraints).
- Figure outputs are written to `data/`.
- Training artifacts from CatBoost are written to `catboost_info/`.

## Metric Interpretation Note

In the current notebook, one binary label is derived from a threshold on `Mortality_Risk`. If `Mortality_Risk` is also used as an input feature, near-perfect classification metrics are expected because the model is learning a threshold mapping.

If you want stricter, leakage-resistant evaluation, use features that do not directly define the target.

## Git Tracking Notes

- `catboost_info/` is ignored in `.gitignore`.
- Generated figure files are ignored by `data/.gitignore` (`fig*.png`).

## License

See `LICENSE`.
