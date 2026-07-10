# Titanic Survival Prediction

## Project Overview
This project predicts whether a Titanic passenger survived using a classic classification dataset. It shows the full workflow of data analysis, preprocessing, feature engineering, model training, and evaluation.

## Major Issues Observed
- The project is notebook-driven, so it could benefit from a more structured pipeline and clearer explanation of each step.
- The repository would be stronger with more consistent model comparison and better documentation of feature choices.

---

## ✨ Features

- 📊 **Exploratory Data Analysis** - Understand the dataset deeply
- 🧹 **Data Preprocessing** - Handle missing values professionally
- ⚙️ **Feature Engineering** - Create powerful features
- 🤖 **Multiple Models** - Compare different algorithms
- 📈 **Model Evaluation** - ROC curves, confusion matrices
- 🎯 **Classification Metrics** - Accuracy, Precision, Recall, F1
- 📊 **Beautiful Visualizations** - Publication-quality plots

---

## 📚 Dataset Overview

### The Titanic Dataset
- **891 passengers** in training set
- **418 passengers** in test set  
- **Outcome**: Survived (1) or Did Not Survive (0)
- **Features**: 11 input features (age, ticket class, gender, etc.)

### Key Features

| Feature | Description | Type |
|---------|-------------|------|
| **Pclass** | Ticket class (1st, 2nd, 3rd) | Ordinal |
| **Sex** | Passenger gender | Categorical |
| **Age** | Age in years | Numerical |
| **SibSp** | Number of siblings/spouses | Numerical |
| **Parch** | Number of parents/children | Numerical |
| **Fare** | Ticket price | Numerical |
| **Embarked** | Port of embarkation | Categorical |
| **Cabin** | Cabin identifier | Categorical |
| **Name** | Passenger name | Text |

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Jupyter Notebook
- pip package manager

### 📦 Installation

```bash
# Clone repository
git clone https://github.com/yourusername/titanic-prediction.git
cd titanic-prediction

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

## 📁 Project Structure

```
🚢 Titanic Prediction/
├── 📂 data/                    # Dataset directory
│   ├── train.csv              # Training data
│   ├── test.csv               # Test data
│   └── [other datasets]
├── 📂 notebooks/              # Jupyter notebooks
│   ├── 📘 EDA.ipynb           # Exploratory Data Analysis
│   ├── 📘 preprocessing.ipynb  # Data cleaning
│   ├── 📘 feature_engineering.ipynb
│   └── 📘 modeling.ipynb      # Model training
├── 📂 images/                 # Visualizations
│   ├── roc_curve.png
│   ├── confusion_matrix.png
│   ├── missing_values.png
│   └── [other plots]
├── 📄 requirements.txt        # Dependencies
└── 📄 README.md              # This file
```

---

## 🔍 Analysis Pipeline

```
┌──────────────────────────┐
│    Load Data             │
│  train.csv & test.csv    │
└──────────────┬───────────┘
               ▼
┌──────────────────────────┐
│  Exploratory Analysis    │
│  - Visualizations        │
│  - Correlations          │
│  - Missing values        │
└──────────────┬───────────┘
               ▼
┌──────────────────────────┐
│  Data Preprocessing      │
│  - Handle missing data   │
│  - Encode categorical    │
│  - Scale features        │
└──────────────┬───────────┘
               ▼
┌──────────────────────────┐
│ Feature Engineering      │
│  - Create new features   │
│  - Select best features  │
│  - Handle outliers       │
└──────────────┬───────────┘
               ▼
┌──────────────────────────┐
│  Train-Test Split        │
│  - 80% training          │
│  - 20% testing           │
└──────────────┬───────────┘
               ▼
┌──────────────────────────┐
│  Model Training          │
│  - Logistic Regression   │
│  - Multiple models       │
│  - Cross-validation      │
└──────────────┬───────────┘
               ▼
┌──────────────────────────┐
│  Model Evaluation        │
│  - ROC curve             │
│  - Confusion matrix      │
│  - Performance metrics   │
└──────────────────────────┘
```

---

## 🎯 Key Insights

### Survival Factors

✅ **Higher survival rate with:**
- Female passengers
- 1st class tickets
- Younger age
- Traveling with family

❌ **Lower survival rate with:**
- Male passengers
- 3rd class tickets
- Older passengers
- Traveling alone

---

## 🤖 Models Used

### Logistic Regression
```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()
model.fit(X_train, y_train)
accuracy = model.score(X_test, y_test)
```

### Evaluation Metrics

| Metric | Formula | Interpretation |
|--------|---------|----------------|
| **Accuracy** | (TP+TN)/(TP+TN+FP+FN) | Overall correctness |
| **Precision** | TP/(TP+FP) | False alarm rate |
| **Recall** | TP/(TP+FN) | Missing rate |
| **F1 Score** | 2*(Precision*Recall)/(Precision+Recall) | Balance metric |

---

## 📊 Tech Stack

| Component | Technology |
|-----------|-------------|
| **Data Processing** | Pandas |
| **Numerical Computation** | NumPy |
| **Machine Learning** | scikit-learn |
| **Visualization** | Matplotlib, Seaborn |
| **Notebooks** | Jupyter |
| **Statistics** | SciPy, Statsmodels |

---

## 📈 Performance Results

**Example Model Performance:**

```
              precision    recall  f1-score   support

       Died       0.81      0.84      0.82       106
   Survived       0.78      0.74      0.76        72

    accuracy                           0.80       178
   macro avg       0.79      0.79      0.79       178
weighted avg       0.80      0.80      0.80       178
```

---

## 🎓 Learning Outcomes

After completing this project, you'll understand:

✅ How to explore and analyze datasets

✅ Handling missing values and outliers

✅ Feature engineering and selection

✅ Training and evaluating classification models

✅ Interpreting ROC curves and confusion matrices

✅ Cross-validation and hyperparameter tuning

✅ Building production-ready ML pipelines

---

## 🚢 Historical Context

The Titanic sank on April 15, 1912, resulting in:
- **1,502 deaths** out of 2,224 passengers and crew
- **Women and children** were prioritized in lifeboats
- **Class disparities** were significant in survival

This dataset has become a benchmark for machine learning!

---

## 🤝 Contributing

Contributions welcome:
- Improve models
- Add new features
- Try different algorithms
- Enhance visualizations


---

## 📚 Resources

- [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic)
- [scikit-learn Documentation](https://scikit-learn.org/)
- [Pandas Documentation](https://pandas.pydata.org/)

---

## Enhanced Documentation - Learning Review

### Project Overview

This project analyzes Titanic passenger survival and trains a Logistic Regression classifier. The analysis script performs exploratory checks, missing-value handling, outlier capping, feature engineering, categorical encoding, robust scaling, train/test splitting, and evaluation with classification metrics, ROC curve, and confusion matrix.


### Features

- Titanic survival classification workflow.
- Missing value analysis and heatmap visualization.
- Age and embarked imputation.
- Cabin availability feature engineering.
- Outlier thresholding for fare.
- Rare category encoding, one-hot encoding, and robust scaling.
- Logistic Regression model with ROC and confusion matrix visualizations.

### Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter-compatible Python script workflow

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Usage

The analysis is stored as a Python script:

```bash
python notebooks\titanic_analysis.py
```

Important path note: the script currently reads `kaggle_datasets/train.csv`, while the inspected repository contains `data/train.csv`. Update the path locally or run from a folder layout that contains the expected `kaggle_datasets/train.csv`.

### Folder Structure

```text
Titanic-survival-prediction-project_10/
|   .gitignore
|   CODE_OF_CONDUCT.md
|   CONTRIBUTING.md
|   LICENSE
|   README.md
|   requirements.txt
|   SECURITY.md
|
+---.github
|   |   pull_request_template.md
|   |
|   \---ISSUE_TEMPLATE
|           bug_report.md
|           custom.md
|           feature_request.md
|
+---data
|       train.csv
|
+---images
|       boxplot_iqr.png
|       confusion_matrix.png
|       missing_value.png
|       roc_curve.png
|
\---notebooks
        titanic_analysis.py
```

### Workflow

1. Load Titanic training data.
2. Inspect missing values and distributions.
3. Fill missing `Embarked` and `Age` values.
4. Convert cabin presence into `CABIN_BOOL`.
5. Detect and cap fare outliers.
6. Generate features such as ticket length, title, age group, and fare category.
7. Encode categorical variables and scale numerical variables.
8. Train Logistic Regression.
9. Evaluate with accuracy, precision, recall, F1, ROC-AUC, ROC curve, and confusion matrix.

### Dataset Information

- Dataset file present: `data/train.csv`
- Observed rows: 891
- Columns: `PassengerId`, `Survived`, `Pclass`, `Name`, `Sex`, `Age`, `SibSp`, `Parch`, `Ticket`, `Fare`, `Cabin`, `Embarked`
- No separate `test.csv` file was found in the inspected project tree.

### Model Information

- Model used in script: `LogisticRegression(max_iter=1000)`
- Train/test split: 80/20 with stratification.
- Evaluation metrics are printed at runtime.
- Saved model artifact is not present.

### Important Files Verified

- `requirements.txt`: present
- `notebooks/titanic_analysis.py`: present
- `data/train.csv`: present
- `images/`: present
- `LICENSE`: present
- `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY.md`: present
- `app.py`, `main.py`, `train.py`, `predict.py`: not present

### Future Improvements

- Fix the dataset path in `titanic_analysis.py` or document the expected folder layout.
- Save generated model artifacts if future inference is needed.
- Add a notebook version with outputs preserved for easier review.
- Add model comparison with Random Forest, SVM, or Gradient Boosting only if metrics are generated and reported honestly.

### Learning Notes

- This project demonstrates an end-to-end tabular classification workflow.
- Feature engineering can improve classic baseline models like Logistic Regression.
- Reproducible paths and saved outputs make analysis projects easier for others to run.

### Credits

- Original author referenced in the MIT License: Hasan Pireci.
- Dataset source referenced by the original README: Kaggle Titanic competition.
- Documentation enhanced for educational review and learning.

### License

This project includes an MIT License.