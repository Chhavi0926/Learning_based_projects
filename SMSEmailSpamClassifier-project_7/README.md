# SMS/Email Spam Classifier

## Project Overview
This project classifies messages as spam or ham using NLP techniques such as preprocessing, TF-IDF, and a machine learning classifier. It is a practical example of applying text classification in a simple user-friendly app.

## Major Issues Observed
- The project depends on NLTK data downloads, which can be a minor obstacle for new users.
- The model pipeline would be easier to maintain with clearer evaluation metrics and better packaging.

## Features

- Fast spam detection
- High accuracy (95%+)
- Mobile-friendly interface
- NLP preprocessing
- Pre-trained model included

## How It Works

```
┌──────────────────────────────┐
│    User Input (SMS/Email)      │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│      Text Preprocessing        │
│  - Lowercase conversion       │
│  - Tokenization               │
│  - Stopword removal           │
│  - Stemming                   │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│     TF-IDF Vectorization      │
│  - Feature extraction        │
│  - Weight calculation        │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│      ML Classifier             │
│  - Naive Bayes Model         │
│  - Spam/Ham prediction       │
└──────────┬───────────────────┘
             ▼
┌──────────────────────────────┐
│      Result Display           │
│  - Spam or Not Spam          │
│  - Confidence score          │
└──────────────────────────────┘
```

---

## 📦 Project Structure

```
📬-spam-classifier/
├── 📄 app.py                # Streamlit application
├── 📊 model.pkl             # Trained classifier model
├── 📊 vectorizer.pkl        # TF-IDF vectorizer
├── 📄 requirements.txt      # Dependencies
├── 📄 nltk.txt              # NLTK resources
└── 📄 README.md            # This file
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip package manager

### 📥 Installation

```bash
# Clone repository
git clone https://github.com/yourusername/spam-classifier.git
cd spam-classifier

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Download NLTK data
python -m nltk.downloader punkt stopwords
```

### ▶️ Running the App

```bash
streamlit run app.py
```

Then open your browser to:
```
http://localhost:8501
```

---

## 📊 Input & Output

### Input
- Any SMS or email message (text)

### Output
- **Spam** - Message is likely spam 😨
- **Not Spam** - Message is legitimate 😄
- **Confidence** - Classification confidence score

---

## 🛠️ NLP Pipeline

### Text Preprocessing
1. **Lowercase** - Convert to lowercase
2. **Tokenization** - Split into words (NLTK)
3. **Stopword Removal** - Remove common words
4. **Stemming** - Reduce to root form (Porter Stemmer)

### Feature Extraction
- **TF-IDF Vectorization** - Convert text to numerical features
- **Term Frequency** - How often words appear
- **Inverse Document Frequency** - Uniqueness of words

### Classification
- **Naive Bayes** - Probability-based classifier
- **Training Data** - 5,000+ SMS messages
- **Accuracy** - ~95% on test set

---

## 💪 Model Performance

| Metric | Value |
|--------|-------|
| **Accuracy** | 95%+ |
| **Precision** | 94% |
| **Recall** | 96% |
| **F1 Score** | 0.95 |
| **Training Data** | 5,000+ messages |

---

## 💫 Example Usage

1. Open app: http://localhost:8501
2. Paste SMS/email in text area:
   ```
   "Congratulations! You've won ₹1,00,000. Claim now!"
   ```
3. Click "Predict" button
4. View result: **SPAM** 😨

---

## 📈 Tech Stack

| Component | Technology |
|-----------|-------------|
| **Framework** | Streamlit |
| **ML Model** | scikit-learn |
| **NLP** | NLTK |
| **Vectorization** | TF-IDF |
| **Deployment** | Streamlit Cloud ready |

---

## 🐞 API Usage (Optional)

If extending to API:

```python
from app import transform_text, model, tfidf

message = "Get free credit card now!"
clean_text = transform_text(message)
vector = tfidf.transform([clean_text])
prediction = model.predict(vector)[0]
print("Spam" if prediction == 1 else "Not Spam")
```

---

## �� Deployment

### Deploy to Streamlit Cloud

1. Push code to GitHub
2. Go to [streamlit.io](https://streamlit.io)
3. Connect GitHub repository
4. Deploy automatically!

### Deploy Elsewhere
- **Heroku**: Create Procfile
- **Docker**: Containerize with Dockerfile
- **AWS**: Lambda + API Gateway

---

## 🗐️ Notes

✅ Pre-trained models included - no training needed

✅ Works with any SMS or email message

✅ Mobile-responsive interface

✅ Fast inference (<100ms per message)

✅ Can be extended with more training data




---

## Enhanced Documentation - Learning Review

### Project Overview

This project is a Streamlit SMS/email spam classifier. It preprocesses text with NLTK, transforms the cleaned message with a saved TF-IDF vectorizer, and classifies the result using a saved pickled model.



### Features

- Streamlit web UI for message classification.
- NLTK tokenization, stopword removal, and Porter stemming.
- Saved vectorizer file: `vectorizer.pkl`.
- Saved classifier file: `model.pkl`.
- Demo GIF included.
- Nested duplicate project folder under `SMS_Spam_Detection/`.

### Technologies Used

- Python
- Streamlit
- NLTK
- scikit-learn
- Pickle

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python -m nltk.downloader punkt stopwords
```

### Usage

```bash
streamlit run app.py
```

Then open the Streamlit URL shown in the terminal, usually `http://localhost:8501`.

### Folder Structure

```text
SMSEmailSpamClassifier-project_7/
|   app.py
|   demo.gif
|   LICENSE
|   model.pkl
|   nltk.txt
|   README.md
|   requirements.txt
|   vectorizer.pkl
|
+---.devcontainer
|       devcontainer.json
|       nltk.txt
|       setup.sh
|
+---.idea
|   |   .gitignore
|   |   misc.xml
|   |   modules.xml
|   |   SMS-Email-Spam-Classifier.iml
|   |   vcs.xml
|   |
|   \---inspectionProfiles
|           profiles_settings.xml
|
\---SMS_Spam_Detection
    \---SMS-Email-Spam-Classifier
            app.py
            LICENSE
            model.pkl
            README.md
            requirements.txt
            vectorizer.pkl
```

### Workflow

1. User enters an SMS or email message in the Streamlit text area.
2. `transform_text()` lowercases, tokenizes, removes non-alphanumeric tokens, removes stopwords, and stems words.
3. `vectorizer.pkl` converts the cleaned text into TF-IDF features.
4. `model.pkl` predicts spam or not spam.
5. Streamlit displays the classification result.

### Dataset Information

- No raw training dataset file is present in the inspected project tree.
- The README references SMS/email spam training data, but the dataset itself is not included.

### Model Information

- Model artifact: `model.pkl`
- Vectorizer artifact: `vectorizer.pkl`
- Training script/notebook is not present, so model type and metrics cannot be independently verified from source files.
- Existing README metric claims are preserved as original content; no new metrics are added here.

### Important Files Verified

- `requirements.txt`: present
- `app.py`: present
- `model.pkl`: present
- `vectorizer.pkl`: present
- `nltk.txt`: present
- `demo.gif`: present
- Nested project copy: present
- `LICENSE`: present

### Future Improvements

- Add the training notebook or script used to create `model.pkl`.
- Add a model evaluation report generated from a held-out test set.
- Cache NLTK stopwords for faster repeated predictions.
- Avoid downloading NLTK data on every app startup when already available.

### Learning Notes

- Text preprocessing must match the preprocessing used during training.
- Pickled ML artifacts should be loaded only from trusted sources.
- Streamlit is useful for quickly turning an NLP model into an interactive app.

### Credits

- Original author referenced in the MIT License: Kunal Bandale.
- Documentation enhanced for educational review and learning.

### License

This project includes an MIT License. 