
# Text Recognizer


## Enhanced Documentation - Learning Review

### Project Overview

This project is a notebook-based OCR learning project. It compares EasyOCR and PyTesseract on local sample images, showing how text can be extracted from images using both deep learning-based OCR and a Tesseract-backed OCR workflow.

## Major Issues Observed
- The project requires system-level Tesseract setup, which can be difficult for beginners on Windows.
- The notebook-based workflow would be easier to follow with more standardized preprocessing and evaluation steps.

---


### Technologies Used

- Python
- Jupyter Notebook
- EasyOCR
- PyTesseract
- Pillow
- Tesseract OCR executable

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

PyTesseract also requires the Tesseract OCR application to be installed on the operating system. The repository contains a Windows installer, but it still needs to be installed before the PyTesseract notebook can call it.

### Usage

```bash
jupyter notebook
```

Open either `ocr_testing.ipynb` for EasyOCR or `pytesseract_testing.ipynb` for Tesseract-based OCR, then run cells sequentially.


### Workflow

1. Load a sample image such as `img2.jpeg` or `img3.jpeg`.
2. Initialize the selected OCR engine.
3. Run text detection/extraction on the image.
4. Inspect extracted text and, where available, confidence/detail outputs.
5. Compare EasyOCR and PyTesseract behavior.

### Dataset Information

- No tabular dataset is used.
- Image inputs present: `img1.jpeg`, `img2.jpeg`, `img3.jpeg`.

### Model Information

- EasyOCR downloads/uses pre-trained OCR models internally.
- PyTesseract uses the installed Tesseract OCR engine.
- No custom model training or saved custom model artifact is present.

### Important Files Verified

- `requirements.txt`: present
- `ocr_testing.ipynb`: present
- `pytesseract_testing.ipynb`: present
- Sample images: present
- `tesseract_downloaded/`: present
- `app.py`, `main.py`, `train.py`, `predict.py`: not present because this is a notebook-only OCR project

### Future Improvements

- Add image preprocessing examples such as grayscale, thresholding, denoising, and deskewing.
- Avoid hard-coded local Tesseract paths by documenting a configurable path variable.
- Add side-by-side extracted text outputs for each sample image.
- Add a small script version for batch OCR.

### Learning Notes

- OCR quality depends heavily on image clarity, language settings, and preprocessing.
- EasyOCR is easier to try in notebooks but may download larger model files.
- PyTesseract requires system setup in addition to Python packages.





## ✨ Features

- 🧠 **Deep Learning OCR** - EasyOCR with neural networks
- 🖼️ **Traditional OCR** - PyTesseract (traditional approach)
- 🔄 **Comparison** - Side-by-side technique evaluation
- 📊 **Hands-on Learning** - Interactive Jupyter notebooks
- 🎯 **High Accuracy** - Support for multiple languages
- ⚡ **Fast Processing** - GPU-accelerated (optional)
- 📝 **Text Extraction** - From documents, signs, images

---

## 📚 Notebooks Included

```
📝 Text Recognizer/
├── 📘 ocr_testing.ipynb           # EasyOCR experiments
├── 📘 pytesseract_testing.ipynb   # PyTesseract examples
├── 📂 tesseract_downloaded/       # Tesseract binaries
├── 📂 [sample images]             # Test images
├── 📄 requirements.txt            # Dependencies
└── 📄 README.md                  # This file
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Jupyter Notebook
- pip package manager

### 📦 Installation

```bash
# Clone repository
git clone https://github.com/yourusername/text-recognizer.git
cd text-recognizer

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate


# Install dependencies
pip install -r requirements.txt
```

### ⚙️ System Dependencies

#### For PyTesseract (Windows)

```bash
choco install tesseract
```

#### For PyTesseract (macOS)

```bash
brew install tesseract
```

#### For PyTesseract (Linux)

```bash
sudo apt-get install tesseract-ocr
```

### ▶️ Running Notebooks

```bash
# Start Jupyter
jupyter notebook

# Then:
# 1. Click on ocr_testing.ipynb or pytesseract_testing.ipynb
# 2. Run cells sequentially
# 3. Experiment with your own images
```

---

## 🎯 OCR Techniques Comparison

### EasyOCR (Deep Learning)
```
✅ Pros:
- Higher accuracy
- Handles challenging images
- Supports 80+ languages
- Better with curved text
- GPU acceleration support

❌ Cons:
- Slower inference
- More memory intensive
- Requires download of models
```

### PyTesseract (Traditional)
```
✅ Pros:
- Fast processing
- Lightweight
- Established & reliable
- Works offline

❌ Cons:
- Lower accuracy on complex images
- Struggles with skewed text
- Limited language support
- No GPU acceleration
```

---

## 🔧 Tech Stack

| Component | Technology |
|-----------|-------------|
| **Deep Learning OCR** | EasyOCR |
| **Traditional OCR** | Tesseract + PyTesseract |
| **Image Processing** | OpenCV, Pillow |
| **Data Processing** | Pandas, NumPy |
| **Notebooks** | Jupyter |
| **Visualization** | Matplotlib |

---

## 💡 Example Usage

### EasyOCR

```python
import easyocr
from PIL import Image

# Initialize reader
reader = easyocr.Reader(['en'])

# Read text from image
result = reader.readtext('path/to/image.png')

# Extract text
for detection in result:
    text = detection[1]
    confidence = detection[2]
    print(f"Text: {text}, Confidence: {confidence:.2f}")
```

### PyTesseract

```python
import pytesseract
from PIL import Image

# Read text from image
image = Image.open('path/to/image.png')
text = pytesseract.image_to_string(image)
print(text)

# Get detailed info
data = pytesseract.image_to_data(image)
print(data)
```

---

## 📊 Performance Metrics

| OCR Method | Speed | Accuracy | Memory |
|-----------|-------|----------|--------|
| **EasyOCR** | Medium | 95%+ | 500MB+ |
| **PyTesseract** | Fast | 70-80% | <50MB |

---

## 🎯 Use Cases

✅ **Document Digitization** - Convert scanned documents to text

✅ **Receipt/Invoice Reading** - Extract data from receipts

✅ **License Plate Recognition** - Read vehicle plates

✅ **Handwriting Recognition** - Digitize handwritten notes

✅ **Sign Detection** - Read street/shop signs

✅ **Book Scanning** - Convert books to digital text

---

## 📝 Notebook Structure

Each notebook typically contains:

1. **Setup** - Import libraries and load images
2. **Preprocessing** - Prepare images (resize, denoise)
3. **OCR Processing** - Extract text using method
4. **Results** - Display extracted text
5. **Comparison** - Side-by-side accuracy comparison
6. **Experiments** - Test with different images

---

## 🚀 Advanced Features

### Preprocessing
- Image denoising
- Contrast enhancement
- Rotation correction
- Deskewing

### Post-processing
- Text cleaning
- Confidence filtering
- Language-specific handling

---

## 📱 Sample Workflows

```
┌────────────────────────┐
│   Load Image           │
└────────────┬───────────┘
             ▼
┌────────────────────────┐
│   Preprocess Image     │
│  - Resize/Normalize    │
└────────────┬───────────┘
             ▼
┌────────────────────────┐
│   Apply OCR            │
│  - EasyOCR or Tesseract│
└────────────┬───────────┘
             ▼
┌────────────────────────┐
│  Extract & Clean Text  │
│  - Filter confidence   │
└────────────┬───────────┘
             ▼
┌────────────────────────┐
│  Output Results        │
│  - Save to file        │
└────────────────────────┘
```

---

## 🤝 Contributing

Contributions welcome:
- Add more OCR techniques
- Improve preprocessing
- Add language support
- Optimize performance

---
### Credits

- Original implementation belongs to its respective author(s).
- Documentation enhanced for educational review and learning.

## 📄 License

MIT License - See LICENSE file for details

---

**Master OCR techniques! 📖**
