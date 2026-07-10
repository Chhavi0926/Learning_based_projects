# Bike Price Prediction

## Project Overview
This project is a compact machine learning web app that predicts used bike prices from user input. It is a good example of how a trained model can be wrapped in a simple Flask interface for real-world use.

## Major Issues Observed
- The model files use non-standard extensions, which can confuse beginners during deployment.
- The UI is simple, but input validation and error handling could be improved for a more reliable experience.

## Features

- Real-time price predictions
- Simple web interface
- Pre-trained ML model
- Considers: kilometers, owner type, age, power, brand


## Project Files

- `application.py` - Flask web app
- `updated_model.lb` - Pre-trained model
- `Used_Bikes.csv` - Sample data
- `templates/` - HTML pages (index, result)
- `static/css/` - Styling


## Quick Start

```bash
# Create virtual environment
python -m venv venv

# Activate
# Windows: venv\Scripts\activate

# Install packages
pip install -r requirements.txt

# Run
python application.py
```

Open `http://127.0.0.1:5050` in your browser.

## How It Works

1. Enter bike details (kilometers, owner type, age, power, brand)
2. Click predict button
3. Get instant price estimate

## Tech Stack

- Flask (web framework)
- scikit-learn (ML model)
- joblib (model storage)
- Pandas/NumPy (data processing)
- HTML/CSS (interface)

---

## Enhanced Documentation - Learning Review

### Project Overview

This project is a Flask-based used bike price prediction application. The application loads a pre-trained model from `updated_model.lb`, accepts bike details through an HTML form, converts selected brand values into numeric labels, and returns a predicted resale price.

This repository is part of my learning journey where I analyze, understand and learn from open-source Machine Learning projects. The original implementation belongs to its respective author(s). I have enhanced the documentation and repository organization for educational purposes only.

### Features

- Flask web interface for entering bike details.
- Pre-trained model artifacts: `updated_model.lb` and `rf_model.lb`.
- Uses `Used_Bikes.csv` as the available dataset.
- HTML templates for input and result display.
- CSS styling under `static/css/`.

### Technologies Used

- Python
- Flask
- NumPy
- Pandas
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

```bash
python application.py
```

Then open `http://127.0.0.1:5050`.

### Folder Structure

```text
BIke_Deployment-project_1/
|   application.py
|   Bike_notebook.ipynb
|   deploy_commands.txt
|   LICENSE
|   README.md
|   requirements.txt
|   rf_model.lb
|   updated_model.lb
|   Used_Bikes.csv
|
+---static
|   \---css
|           style.css
|
\---templates
        index.html
        result.html
```

### Workflow

1. User opens the Flask web form.
2. User enters kilometers driven, ownership type, bike age, engine power, and brand.
3. The app maps bike brand names to numeric values.
4. The loaded model predicts the used bike price.
5. The prediction is rendered back on the web page.

### Dataset Information

- Dataset file: `Used_Bikes.csv`
- Observed rows: 32,648
- Columns: `bike_name`, `price`, `city`, `kms_driven`, `owner`, `age`, `power`, `brand`

### Model Information

- Model files present: `updated_model.lb`, `rf_model.lb`
- Runtime model used by `application.py`: `updated_model.lb`
- The exact training metrics are not included in the repository, so no new accuracy or error claims are added here.

### Important Files Verified

- `requirements.txt`: present
- `application.py`: present
- `updated_model.lb`: present
- `rf_model.lb`: present
- `templates/`: present
- `static/`: present
- `Used_Bikes.csv`: present
- `Bike_notebook.ipynb`: present

### Future Improvements

- Add server-side validation for numeric and categorical inputs.
- Replace hard-coded brand mapping with a saved preprocessing pipeline.
- Add model evaluation metrics from the training notebook.
- Improve error handling when model files are missing.

### Learning Notes

- This project demonstrates the basic pattern of deploying a trained ML model with Flask.
- Preprocessing used during training should be saved and reused during inference to avoid mismatches.
- Documentation should clearly identify which model artifact is actually loaded by the app.

### Credits

- Original author referenced in the MIT License: Ranjit Singh.
- Documentation enhanced for educational review and learning.

### License

This project includes an MIT License.
