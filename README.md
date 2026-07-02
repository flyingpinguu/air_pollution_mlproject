# Air Pollution PM2.5 Prediction

Machine-learning project for predicting daily PM2.5 air pollution from weather and Sentinel-5P satellite features.

## Project Shape

- `eda_cleaning.ipynb`: cleaning, leakage removal, train/validation/test exports
- `location_feature_engineering.ipynb`: latitude and relative-longitude proxy engineering
- `xgboost_rolling.ipynb`: final XGBoost pipeline with rolling features and residual correction
- `random_forest_baseline_not_final.ipynb`: Random Forest baseline/model comparison; not the final submitted model
- `baseline_model.ipynb`: simple baseline experiments

## Final Approach

The retained final model uses XGBoost with:

- cleaned weather and satellite features
- engineered latitude and relative-longitude proxies
- current-day rolling averages by location
- `log1p` target transformation
- out-of-fold residual correction

Raw data and generated CSVs are not committed. Place the competition files in `data/` locally when reproducing the notebooks.

## Setup

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
