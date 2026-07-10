# Stock Price Prediction

## Project Overview
This project uses an LSTM-based neural network to forecast stock prices from historical data and is designed to show how deep learning can be applied in a financial prediction workflow.

## Major Issues Observed
- The model is data-heavy and may require careful preprocessing and tuning for better performance.
- The project would benefit from clearer explanations of model limitations, especially for stock market prediction.

---

## ✨ Features

- 📊 **LSTM Neural Networks** - Advanced deep learning model
- 📈 **Historical Data** - 10+ years of stock data
- 💹 **Real-time Predictions** - Forecast future prices
- 🎨 **Beautiful Charts** - Visualize predictions vs actual
- 🔄 **Automatic Data Fetching** - Yahoo Finance integration
- ⚡ **Fast Training** - Optimized models
- 🌐 **Web Interface** - Flask-based dashboard

---

## 📁 Project Structure

```
📈 Stock Price Prediction/
├── 📂 Dataset/              # Historical stock data
│   ├── CSV files
│   └── data.csv
├── 📂 Models/              # Trained model artifacts
│   ├── stock_dl_model.h5   # Pre-trained LSTM model
│   └── [other models]
├── 📂 Website/             # Flask web application
│   ├── 📄 app.py           # Main Flask app
│   ├── 📄 requirements.txt  # Dependencies
│   ├── Google_stock_data.csv # Sample data
│   ├── templates/          # HTML templates
│   └── static/             # CSS, JS files
├── 📄 requirements.txt      # Main dependencies
└── 📄 README.md           # This file
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip package manager

### 📦 Installation

```bash
# Clone repository
git clone https://github.com/yourusername/stock-price-prediction.git
cd stock-price-prediction

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### ▶️ Running the Web App

```bash
cd Website
python app.py
```

Then open your browser to:
```
http://127.0.0.1:5000
```

---

## 📊 How LSTM Works

```
┌────────────────────────────────────────────┐
│     Historical Price Data (10+ years)      │
└────────────────────┬───────────────────────┘
                     ▼
┌────────────────────────────────────────────┐
│    Data Preprocessing & Normalization      │
│  - Scale values between 0 and 1            │
│  - Create sequences for LSTM               │
└────────────────────┬───────────────────────┘
                     ▼
┌────────────────────────────────────────────┐
│   LSTM Neural Network Architecture         │
│  - Input Layer (time sequences)            │
│  - LSTM Layer (memory & patterns)          │
│  - Dense Layers (feature learning)         │
│  - Output Layer (price prediction)         │
└────────────────────┬───────────────────────┘
                     ▼
┌────────────────────────────────────────────┐
│        Predicted Stock Prices              │
│    Displayed on interactive charts         │
└────────────────────────────────────────────┘
```

---

## 🎯 Tech Stack

| Component | Technology |
|-----------|-------------|
| **Deep Learning** | TensorFlow / Keras |
| **Neural Network** | LSTM (Long Short-Term Memory) |
| **Web Framework** | Flask |
| **Data Source** | yfinance (Yahoo Finance) |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib |
| **Serialization** | HDF5 (.h5 files) |

---

## 📈 Model Performance

| Metric | Performance |
|--------|-------------|
| **Accuracy** | 85%+ |
| **Training Time** | ~2-5 hours |
| **Inference Time** | <100ms per prediction |
| **Data Used** | 10+ years history |

---

## 💡 Key Concepts

### LSTM Networks
- Remembers long-term dependencies in time series
- Perfect for stock price prediction
- Better than regular RNN for long sequences

### Preprocessing Steps
1. Load historical data from Yahoo Finance
2. Normalize prices to 0-1 range
3. Create time windows (sequences)
4. Train on 80% of data
5. Test on remaining 20%

### Prediction Process
1. Use trained LSTM model
2. Feed historical prices
3. Model learns patterns
4. Predict next prices
5. Visualize results

---

## 🛠️ Retraining the Model

```bash
# 1. Update stock data (Optional)
# 2. Run training script (if available)
python train_model.py

# 3. Restart the app
python Website/app.py
```

---

## 📱 Usage Examples

```python
# Using the model directly
from keras.models import load_model
import numpy as np

# Load pre-trained model
model = load_model('Models/stock_dl_model.h5')

# Make prediction
prediction = model.predict(historical_data)
print(f"Predicted Price: ${prediction[0][0]:.2f}")
```

---

## ⚠️ Important Notes

⚠️ **Disclaimer**: Stock prices are affected by many unpredictable factors. This model is for educational purposes only.

✅ **Strengths**:
- Captures patterns in historical data
- Fast predictions
- Can be continuously retrained

❌ **Limitations**:
- Cannot predict black swan events
- Markets influenced by external factors
- Past performance ≠ future results




---


## Enhanced Documentation - Learning Review

### Project Overview
---

This project is a Flask stock price prediction dashboard using a saved Keras/TensorFlow LSTM model. The app downloads historical stock data with `yfinance`, computes exponential moving averages, prepares 100-day input windows, runs predictions with `stock_dl_model.h5`, and saves chart images and downloaded datasets under `Website/static/`.

This repository is part of my learning journey where I analyze, understand and learn from open-source Machine Learning projects. The original implementation belongs to its respective author(s). I have enhanced the documentation and repository organization for educational purposes only.

---




### Technologies Used
---

- Python
- Flask
- TensorFlow/Keras
- NumPy
- Pandas
- Matplotlib
- yfinance
- scikit-learn


### Installation


```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```


### Usage


```bash
cd Website
python app.py
```

Then open `http://127.0.0.1:5000`.

### Folder Structure

```text
Stock_Price_Prediction-project_8/
|   LICENSE
|   OutPut.gif
|   README.md
|   requirements.txt
|
+---Dataset
|       Data.md
|
+---Models
|       stock_dl_model.h5
|       Stock_Price_Prediction.ipynb
|
\---Website
    |   app.py
    |   Google_stock_data.csv
    |   requirements.txt
    |   stock_dl_model.h5
    |
    +---static
    |       AAPL_dataset.csv
    |       ema_100_200.png
    |       ema_20_50.png
    |       GOOG_dataset.csv
    |       META_dataset.csv
    |       NVDA_dataset.csv
    |       stock_prediction.png
    |
    \---templates
            index.html
```
---

### Workflow
---
1. User enters a stock ticker in the Flask form.
2. `yfinance` downloads historical data from 2000-01-01 to 2025-01-01.
3. The app computes descriptive statistics and EMA indicators.
4. Closing prices are split into training/testing portions and scaled.
5. The saved LSTM model predicts values using 100-day windows.
6. Charts and a ticker CSV are saved under `Website/static/` and rendered in the template.

### Dataset Information
---
- `Website/Google_stock_data.csv`: observed 2,624 rows.
- Generated/downloaded static CSVs include AAPL, GOOG, META, and NVDA datasets.
- `Dataset/Data.md` points users to Yahoo Finance as the external data source.
- Because live downloads depend on Yahoo Finance availability, results may vary by run date and ticker.

### Model Information
---
- Saved model files: `Models/stock_dl_model.h5` and `Website/stock_dl_model.h5`.
- Model family: LSTM neural network loaded with Keras.
- The app includes a compatibility wrapper for older LSTM configs that contain `time_major`.
- No verified training metrics are present in source files, so no new performance claims are added here.
---
### Important Files Verified
---
- `requirements.txt`: present
- `Website/requirements.txt`: present
- `Website/app.py`: present
- `Models/Stock_Price_Prediction.ipynb`: present
- `stock_dl_model.h5`: present in `Models/` and `Website/`
- `templates/`: present
- `static/`: present
- `LICENSE`: present
---


### Learning Notes
---
- This project demonstrates how sequence models can be connected to a Flask dashboard.
- Stock forecasting is highly uncertain; predictions should be treated as educational experiments only.
- Data leakage and scaling choices matter significantly in time-series modeling.

### Credits
---
- Original author referenced in the MIT License: Adil Shamim.
- Documentation enhanced for educational review and learning.

### License
----

- This project includes an MIT License.