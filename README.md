# Porosity Prediction from Seismic Attributes (ML Workflow with Uncertainty Quantification)

A reproducible machine-learning workflow for predicting reservoir **porosity (PHIT)** from
seismic attributes, with model comparison and **uncertainty quantification (UQ)**.

This repository accompanies my undergraduate thesis:

> **Seismic Attributes Prediction of Porosity Using Machine Learning with Uncertainty
> Quantification: A Case Study of Inas Field, North Malay Basin**
> Thesis: https://repository.its.ac.id/127681/

## ⚠️ Data
The field data from the original study (well logs and seismic attributes) are **proprietary
and are NOT included** in this repository. The notebook uses **fully synthetic data** generated
in-code, so the methodology is reproducible and self-contained. The workflow and models mirror
the thesis; only the data is synthetic.

## Methods
- Feature correlation analysis and selection
- Blind-well hold-out for spatial generalisation testing
- XGBoost regression with `HalvingRandomSearchCV` hyperparameter tuning
- Model comparison: XGBoost, CatBoost, Random Forest, Quantile Random Forest
- Uncertainty quantification via bootstrap resampling (*Stochastic XGBoost*), 95% CI
- Metrics: RMSE, R², Pearson correlation (PCC)

## Getting started
```bash
pip install -r requirements.txt
jupyter notebook porosity_prediction_ml_workflow.ipynb
```

## Applying to real data
Replace the synthetic-data section with your own loader (e.g. `lasio` for LAS well logs)
and adjust the attribute list. The rest of the workflow is data-agnostic.
