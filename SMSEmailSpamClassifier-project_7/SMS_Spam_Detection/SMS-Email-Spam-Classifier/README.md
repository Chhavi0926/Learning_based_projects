# SMS-Email-Spam-Classifier

## Enhanced Documentation - Learning Review

### Project Overview

This nested project copy contains a Streamlit SMS/email spam classifier. It loads `vectorizer.pkl` and `model.pkl`, preprocesses user text with NLTK, and displays whether the message is spam or not spam.

This repository is part of my learning journey where I analyze, understand and learn from open-source Machine Learning projects. The original implementation belongs to its respective author(s). I have enhanced the documentation and repository organization for educational purposes only.

### Features

- Streamlit text input interface.
- NLTK tokenization, stopword removal, and stemming.
- Pickled TF-IDF vectorizer.
- Pickled classifier model.

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

### Folder Structure

```text
SMS-Email-Spam-Classifier/
    app.py
    LICENSE
    model.pkl
    README.md
    requirements.txt
    vectorizer.pkl
```

### Workflow

1. Enter a message.
2. Clean and stem text with NLTK.
3. Convert cleaned text with the saved vectorizer.
4. Predict with the saved model.
5. Display spam or not spam.

### Dataset Information

No raw training dataset is present in this nested folder.

### Model Information

- `model.pkl`: saved classifier.
- `vectorizer.pkl`: saved TF-IDF vectorizer.
- Training code and verified metrics are not present in this nested folder.

### Future Improvements

- Add training source code and evaluation metrics.
- Avoid repeated NLTK downloads after first setup.
- Add clearer deployment instructions.

### Learning Notes

- This folder appears to duplicate the root spam classifier application.
- Keeping one canonical app folder would reduce maintenance confusion.

### Credits

- Original implementation belongs to its respective author(s).
- Documentation enhanced for educational review and learning.

### License

This nested folder includes an MIT License. The original license file has been kept unchanged.
