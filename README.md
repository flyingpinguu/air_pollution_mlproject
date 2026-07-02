# Air Pollution PM2.5 Prediction

Machine-learning project for predicting daily PM2.5 air pollution from weather and Sentinel-5P satellite features.

## Project Shape

- `eda_cleaning.ipynb`: cleaning, leakage removal, train/validation/test exports
- `sat_eng.ipynb`: latitude proxy from satellite solar-angle patterns
- `relative_longitude_eng.ipynb`: relative longitude proxy from meteorological time-lag correlations
- `xgboost_rolling.ipynb`: final XGBoost pipeline with rolling features and residual correction
- `random_forest.ipynb`: Random Forest model work from the team
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
