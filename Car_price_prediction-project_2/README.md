# Car Price Prediction

## Project Overview
This project combines a FastAPI backend with a Streamlit frontend to provide an end-to-end car price prediction experience. It is a strong example of how machine learning can be exposed through both API and UI layers.

## Major Issues Observed
- The backend and frontend are split into separate folders, so the startup flow can feel slightly confusing for new users.
- The project would benefit from clearer input validation and more consistent dependency management across both services.

## Features

- REST API backend (FastAPI)
- Web interface (Streamlit)
- Linear regression model
- Fast predictions
- Pre-trained and ready to use

## Architecture

```
┌─────────────────────────────────────────┐
│      Streamlit Frontend (UI)            │
│  - Beautiful user interface             │
│  - Form inputs for car features         │
│  - Real-time predictions                │
└────────────┬────────────────────────────┘
             │ HTTP Requests
             ▼
┌─────────────────────────────────────────┐
│      FastAPI Backend (REST API)         │
│  - /predict endpoint                    │
│  - Data validation                      │
│  - Model inference                      │
└────────────┬────────────────────────────┘
             │ Loads
             ▼
┌─────────────────────────────────────────┐
│   ML Model (scikit-learn)               │
│  - LinearRegression trained             │
│  - Feature processing                   │
│  - Price prediction                     │
└─────────────────────────────────────────┘
```

## Project Files

- `app/main.py` - FastAPI backend
- `frontend/app.py` - Streamlit interface
- `LinearRegressionModel.joblib` - Pre-trained model
- `cleaned_car_data.csv` - Training data

## Quick Start

### Backend (FastAPI)
```bash
cd app
pip install -r requirements.txt
python main.py
```

API runs on `http://127.0.0.1:8000`

### Frontend (Streamlit)
```bash
cd frontend
pip install streamlit requests pandas
streamlit run app.py
```

Frontend runs on `http://127.0.0.1:8501`

## Tech Stack

- FastAPI (REST backend)
- Streamlit (web interface)
- scikit-learn (ML model)
- Pandas/NumPy (data processing)
- joblib (model storage)

---

## Enhanced Documentation - Learning Review

### Project Overview

This project predicts used car prices through a FastAPI inference backend and a Streamlit frontend. The backend loads a saved Linear Regression model, validates request payloads with Pydantic, and returns a price prediction. The frontend reads `cleaned_car_data.csv` to populate form controls and sends prediction requests to the local API.


### Features

- FastAPI backend with `/`, `/home`, and `/predict` endpoints.
- Streamlit frontend for interactive prediction.
- Saved model artifacts in both root and `model/`.
- Dockerfile for FastAPI container deployment.
- Jupyter notebooks for model/API experimentation.

### Technologies Used

- Python
- FastAPI
- Streamlit
- Pydantic
- Uvicorn
- Pandas
- NumPy
- scikit-learn
- joblib
- Docker

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

The `app/requirements.txt` file is also present for the API container workflow.

### Usage

Run the API:

```bash
cd app
python main.py
```

Run the frontend in a second terminal:

```bash
cd frontend
streamlit run app.py
```

The API runs on `http://127.0.0.1:8000` and the Streamlit UI usually runs on `http://127.0.0.1:8501`.

### Folder Structure

```text
Car_price_prediction-project_2/
|   .gitattributes
|   Build_push_test_MLapi_docker_images.ipynb
|   cars.csv
|   cleaned_car_data.csv
|   Dockerfile
|   LinearRegressionModel.joblib
|   LinearRegressionModel.pkl
|   predict-car-price.ipynb
|   README.md
|   requirements.txt
|
+---app
|   |   .jovianrc
|   |   main.py
|   |   requirements.txt
|   |
|   \---__pycache__
|           main.cpython-38.pyc
|
+---frontend
|       .jovianrc
|       app.py
|
\---model
        LinearRegressionModel.joblib
        LinearRegressionModel.pkl
```

### Workflow

1. Streamlit loads car names, companies, years, kilometers, and fuel types from `cleaned_car_data.csv`.
2. User selects vehicle details in the frontend.
3. The frontend posts JSON data to FastAPI at `/predict`.
4. FastAPI builds a one-row DataFrame with the expected feature columns.
5. The loaded model returns the predicted car price.

### Dataset Information

- Raw dataset: `cars.csv`
- Cleaned dataset: `cleaned_car_data.csv`
- Observed rows: `cars.csv` has 892 rows; `cleaned_car_data.csv` has 816 rows.
- Key columns: `name`, `company`, `year`, `Price`, `kms_driven`, `fuel_type`



### Important Files Verified

- `requirements.txt`: present
- `app/requirements.txt`: present
- `app/main.py`: present
- `frontend/app.py`: present
- `Dockerfile`: present
- `LinearRegressionModel.joblib`: present
- `LinearRegressionModel.pkl`: present
- `predict-car-price.ipynb`: present

### Future Improvements

- Consolidate duplicate model files and clarify the canonical artifact path.
- Add schema examples for the `/predict` API.
- Add model training/evaluation notes from the notebooks.
- Add validation for unrealistic year and kilometer inputs.

### Learning Notes

- This project demonstrates a useful split between API inference and UI interaction.
- The model expects feature names in a specific order, so request construction must stay aligned with training.
- Keeping backend and frontend dependencies synchronized makes reproduction easier.

### Credits

- Original implementation belongs to its respective author(s).
- Documentation enhanced for educational review and learning.

