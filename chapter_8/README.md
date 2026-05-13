# Chapter 8 Companion —  Supervised Learning for Risk Prediction

This folder contains an  Python companion notebook for Chapter 8 of *Risk Analytics: Machine Learning and Optimization for Data-Driven Decision Making*.

Unlike a static figure-reproduction notebook, this version lets readers change model and risk-analysis assumptions and rerun the analysis.

## Files

- `chapter8_companion.ipynb` —  companion notebook
- `requirements_chapter8.txt` — Python dependencies
- `data/default of credit card clients.xls` — Taiwan credit-card default dataset
- `figures/chapter_8/` — generated figures
- `tables/` — generated CSV tables

## What readers can change

In the `CONFIG` cell, users can modify:

- the feature set used by the models;
- train/validation/test split sizes;
- logistic-regression regularization;
- random-forest hyperparameters;
- gradient-boosting hyperparameters;
- review-capacity levels such as top 5%, 10%, and 20%;
- severity assumptions such as 30%, 50%, and 70%;
- operating thresholds used to convert probabilities into class decisions.

The notebook then refits the models and regenerates the performance tables, expected-loss diagnostics, risk-concentration diagnostics, and figures.

## Recommended setup

```bash
cd path/to/chapter_8
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements_chapter8.txt
python -m ipykernel install --user --name ch8--venv --display-name "Python (ch8--venv)"
```

Open the notebook in VS Code and select the kernel **Python (ch8--venv)**.

## Run order

Run the notebook from top to bottom. To experiment, change the `CONFIG` cell and rerun all cells below it.
