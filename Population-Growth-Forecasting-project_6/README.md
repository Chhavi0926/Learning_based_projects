# Population Growth Forecasting

## Project Overview
This project forecasts future population values for different countries using polynomial regression and a Flask-based web interface. It demonstrates how time-series-style forecasting can be turned into an interactive dashboard.

## Major Issues Observed
- The project would benefit from clearer documentation around the training pipeline and the generated model files.
- The forecasting workflow could be made more robust with better input validation and model versioning.

## Features

- Forecast population for 230+ countries
- Interactive dashboard
- Pre-trained models
- Instant predictions

## Project Files

- `app.py` - Flask application
- `train_model.py` - Training script
- `world_population.csv` - Data
- `population_models.pkl` - Pre-trained models

## Quick Start

```bash
# Install packages
pip install -r requirements.txt

# Run
python app.py
```

Open `http://127.0.0.1:5000` in your browser.

## Tech Stack

- Flask (web framework)
- scikit-learn (polynomial regression)
- Pandas (data processing)
- joblib (model storage)

---

## Enhanced Documentation - Learning Review

### Project Overview

This project forecasts country-level population values using a Flask web app and per-country polynomial regression models. The training script converts wide historical population columns into a long format, trains one degree-2 polynomial regression pipeline per country, and saves both processed data and models with joblib.

### Features

- Flask dashboard for country and year selection.
- Historical population summaries from 1970 to 2022.
- KPI display for growth rate, density, area, and world population percentage.
- Pre-generated model file: `population_models.pkl`.
- Processed long-form data file: `processed_data.pkl`.
- Screenshots folder documenting the UI.

### Technologies Used

- Python
- Flask
- Pandas
- NumPy
- scikit-learn
- joblib
- HTML/CSS

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Usage

Run the existing app:

```bash
python app.py
```

Retrain models if needed:

```bash
python train_model.py
```

### Folder Structure

```text
Population-Growth-Forecasting-project_6/
|   app.py
|   population_models.pkl
|   processed_data.pkl
|   README.md
|   requirements.txt
|   train_model.py
|   world_population.csv
|
+---screenshots
|       keyinsights.png
|       kpis.png
|       main.png
|       visualizations.png
|
+---static
|       style.css
|
\---templates
        index.html
```

### Workflow

1. `train_model.py` reads `world_population.csv`.
2. Historical population columns are reshaped into `Country`, `Year`, and `Population`.
3. A polynomial regression pipeline is trained for each country.
4. Processed data and model dictionary are saved as `.pkl` files.
5. `app.py` loads the saved artifacts and original CSV.
6. The user selects a country and future year to view a forecast and historical context.

### Dataset Information

- Dataset file: `world_population.csv`
- Observed rows: 234
- Key columns include country, capital, continent, population values for 1970 through 2022, area, density, growth rate, and world population percentage.

### Model Information

- Model type used in `train_model.py`: `PolynomialFeatures(degree=2)` with `LinearRegression`.
- Saved model file: `population_models.pkl`
- Processed training data file: `processed_data.pkl`
- The UI variable currently labels `model_type` as `XGBoost`, but the inspected training code uses polynomial regression.

### Important Files Verified

- `requirements.txt`: present
- `app.py`: present
- `train_model.py`: present
- `population_models.pkl`: present
- `processed_data.pkl`: present
- `templates/`: present
- `static/`: present
- `screenshots/`: present
- `world_population.csv`: present

### Future Improvements

- Align the UI model label with the actual polynomial regression model.
- Add input validation for extreme forecast years.
- Add model evaluation or backtesting against held-out historical years.
- Add confidence intervals or uncertainty notes for forecasts.

### Learning Notes

- This project demonstrates converting wide historical data into a model-friendly long format.
- Training one model per country is simple to understand but can become harder to maintain as model complexity grows.
- Forecasts beyond the observed year range should be treated as educational estimates, not authoritative demographic projections.

### Credits

- Original implementation belongs to its respective author(s).
- Documentation enhanced for educational review and learning.

