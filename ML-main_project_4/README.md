# Machine Learning Practice Notebooks

## Project Overview
This repository is a learning-focused collection of regression notebooks that demonstrates core machine learning concepts through practical examples. It is helpful for understanding how different regression models behave on real data.

## Major Issues Observed
- The notebook collection is useful, but the project would benefit from a clearer learning path and better navigation between topics.
- Some notebooks can be improved with more consistent comments and standardized workflow explanations.

## Notebooks Included

- LinearReg.ipynb - Simple linear regression
- MultiLinReg.ipynb - Multiple linear regression
- PolynomialReg.ipynb - Polynomial models
- RidgeReg.ipynb - Ridge regression (L2)
- LassoReg.ipynb - Lasso regression (L1)
- ElasticNetReg.ipynb - Combined regularization

## Datasets

- house_data.csv - 21,613 rows, 21 features
- employee_salary_data.csv - 30 rows, 2 features
- student_performance.csv - 1000+ rows, 16 features
- student_data.csv - 100+ rows, 3 features

## Quick Start

```bash
# Create virtual environment
python -m venv venv

# Activate
# Windows: venv\Scripts\activate


# Install packages
pip install -r requirements.txt

# Run Jupyter
jupyter notebook
```

## Typical Workflow

```
┌──────────────────────────────┐
│       Load Data                    │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│    Exploratory Analysis           │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│   Data Preprocessing              │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│    Train Test Split              │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│     Train Model                  │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│    Evaluate Results              │
└──────────────────────────────┘
```

## Tech Stack

- Jupyter Notebook (interactive development)
- Pandas (data manipulation)
- NumPy (numerical computations)
- scikit-learn (ML algorithms)
- Matplotlib (visualizations)
- Seaborn (statistical plots)

---

## Enhanced Documentation - Learning Review

### Project Overview

This project is a notebook-based machine learning practice collection focused on regression. It includes simple linear regression, multiple linear regression, polynomial regression, Ridge, Lasso, and ElasticNet examples, along with additional Colab-style notebooks that calculate regression metrics such as MAE, MSE, and R2 score.


### Features

- Multiple regression algorithms demonstrated in separate notebooks.
- Small CSV datasets for quick experimentation.
- Examples using train/test split and scikit-learn estimators.
- Regularization notebooks for Ridge, Lasso, and ElasticNet.
- Additional notebooks with metric-based model evaluation.

### Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- scikit-learn
- Matplotlib
- Seaborn

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Usage

```bash
jupyter notebook
```

Open any notebook and run cells sequentially.

### Folder Structure

```text
ML-main_project_4/
    ElasticNetReg.ipynb
    employee_salary_data.csv
    house_data.csv
    LassoReg.ipynb
    LinearReg.ipynb
    MultiLinReg.ipynb
    notebook.ipynb
    notebook1.ipynb
    notebook2.ipynb
    PolynomialReg.ipynb
    README.md
    requirements.txt
    RidgeReg.ipynb
    student_data.csv
    student_performance.csv
```

### Workflow

1. Load one of the included CSV datasets.
2. Select input features and target values.
3. Split data into training and testing sets where applicable.
4. Train the selected regression model.
5. Predict test values or sample values.
6. Evaluate or compare results depending on the notebook.

### Dataset Information

- `employee_salary_data.csv`: 10 rows; columns include experience, education level, skill score, interview score, salary.
- `house_data.csv`: 10 rows; columns include area, bedrooms, house age, price.
- `student_data.csv`: 10 rows; columns include attendance, test marks, assignment marks, practical marks, final marks.
- `student_performance.csv`: 10 rows; columns include study hours, attendance, internal marks, assignment marks, practical marks, final score.

### Model Information

- `LinearReg.ipynb`: Linear Regression.
- `MultiLinReg.ipynb`: Multiple Linear Regression.
- `PolynomialReg.ipynb`: PolynomialFeatures with Linear Regression.
- `RidgeReg.ipynb`: Ridge Regression.
- `LassoReg.ipynb`: Lasso Regression.
- `ElasticNetReg.ipynb`: ElasticNet Regression.
- No saved model artifact is present.

### Important Files Verified

- `requirements.txt`: present
- Regression notebooks: present
- CSV datasets: present
- `app.py`, `main.py`, `train.py`, `predict.py`: not present because this is a notebook-only learning project
- Saved model files: not present

### Future Improvements

- Add one index notebook that explains the recommended learning order.
- Add markdown explanations before each modeling step.
- Save model metrics in each notebook for easier comparison.
- Add a script-based version for one complete regression workflow.

### Learning Notes

- The project is useful for comparing how different regression methods behave on small datasets.
- Regularization notebooks demonstrate how Ridge, Lasso, and ElasticNet differ from ordinary linear regression.
- Small toy datasets are good for learning syntax, but larger datasets are needed for realistic model evaluation.

### Credits

- Original implementation belongs to its respective author(s).
- Documentation enhanced for educational review and learning.

