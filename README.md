# Hotel Reservation Cancellation Prediction

## Project Overview
This project predicts whether a hotel reservation will be canceled using machine learning. The project was developed as part of the SDAIA Academy – Advanced Machine Learning Methods course.

## Problem Statement
The objective is to predict hotel booking cancellations before arrival, allowing hotels to better understand cancellation risk and support operational planning.

## Dataset
- Dataset: Hotel Reservations Dataset
- Source: Kaggle
- Number of records: 36,275
- Target variable: `booking_status`
- Positive class: `Canceled`
- Negative class: `Not_Canceled`
- The raw dataset is not included in this repository.

## Model
XGBoost Classifier was used as the main machine learning model.

## Validation
A stratified validation strategy was used to preserve the target class distribution. Preprocessing was performed within the modelling workflow to reduce data leakage risk.

## Evaluation Metrics
The model was evaluated using:
- ROC-AUC
- PR-AUC
- Precision
- Recall
- Confusion Matrix

The baseline cross-validation PR-AUC was approximately **0.9168**.

## Class Imbalance
Class imbalance was evaluated using class weighting and compared with the baseline model.

## Threshold Optimization
The classification threshold was evaluated using out-of-fold predictions rather than relying only on the default threshold of 0.5.

## Hyperparameter Tuning
A small Optuna hyperparameter search was performed using a fixed validation strategy. The tuned model achieved a PR-AUC of approximately **0.9122**, which did not improve upon the baseline PR-AUC of approximately **0.9168**. Therefore, the baseline model was retained.

## Interpretability
SHAP was used for model interpretability:
- Global feature importance
- Local prediction explanation

Generated SHAP plots are available in the `images/` folder.

## Probability Calibration
Model probability calibration was assessed using a calibration curve and Brier score.

## Repository Structure
- `project.ipynb` – complete project notebook
- `README.md` – project documentation
- `requirements.txt` – required Python libraries
- `data/README.md` – dataset information
- `images/` – generated plots
- `results/` – model evaluation results

## Tools
Python, Pandas, NumPy, Scikit-learn, XGBoost, SHAP, Optuna, and Matplotlib.

## Course
SDAIA Academy – Advanced Machine Learning Methods
