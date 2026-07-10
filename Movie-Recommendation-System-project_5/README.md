# Movie Recommendation System

## Project Overview
This project is a Django-based movie recommendation system that suggests similar movies using content-based filtering and machine learning. It is a strong example of combining a web app with a recommender model and training pipeline.

## Major Issues Observed
- The project is powerful, but the model and training workflow can be heavy for beginners because of the large data and setup requirements.
- The repository would benefit from a simpler training guide and clearer instructions for switching between demo and custom models.

## What is included
- Django project in movie_recommendation/
- Recommendation logic in recommender/
- Training scripts in training/
- Static demo data and assets under static/ and assets/

## Run locally
```bash
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Then open http://127.0.0.1:8000 in your browser.

## Notes
- The project already includes a demo recommendation setup.
- For larger training runs, use the scripts in training/ and update the model paths if needed.
Want to train on more movies or your own dataset? See the [**Training Guide**](training/guide.md) for:

- 📖 Complete training documentation
- 🎯 Configuration options (10K to 1M+ movies)
- ⚙️ Performance tuning guidelines
- 📊 Dataset requirements
- 🔧 Advanced features

**Quick Training Example:**

```python
from training.train import MovieRecommenderTrainer

# Initialize trainer
trainer = MovieRecommenderTrainer(
    output_dir='./models',
    use_dimensionality_reduction=True,
    n_components=500
)

# Train on your dataset
df, sim_matrix = trainer.train(
    'path/to/your/dataset.csv',
    quality_threshold='medium',  # low/medium/high
    max_movies=100000            # Limit dataset size
)
```

**For detailed training instructions**, see:
- 📘 [Training Guide](training/guide.md) - Complete training documentation
- 📘 [PROJECT_GUIDE.md](PROJECT_GUIDE.md#-model-training) - Training setup and configurations

---

## 📡 API Reference

### Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Home page with search interface |
| `/` | POST | Submit movie search and get recommendations |
| `/api/search/` | GET | Search movies (autocomplete) |
| `/api/health/` | GET | Health check endpoint |

### Search Movies

**Request:**
```http
GET /api/search/?q=inception
```

**Response:**
```json
{
  "movies": ["Inception", "Inception: The Cobol Job"],
  "count": 2
}
```

### Health Check

**Request:**
```http
GET /api/health/
```

**Response:**
```json
{
  "status": "healthy",
  "movies_loaded": 100000,
  "model_dir": "./models",
  "model_loaded": true
}
```

For complete API documentation, see [PROJECT_GUIDE.md - API Reference](PROJECT_GUIDE.md#-api-reference)

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file (optional for development):

```env
# Django Settings
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# Model Configuration
MODEL_DIR=./models

# Database (optional - defaults to SQLite)
# DATABASE_URL=postgresql://user:password@localhost/dbname

# Deployment
# RENDER_EXTERNAL_HOSTNAME=your-app.onrender.com
```

### Using Different Models

To switch between models, set the `MODEL_DIR` environment variable:

```bash
# Use demo model (2K movies)
export MODEL_DIR=./static

# Use your trained model (custom)
export MODEL_DIR=./models

# Use absolute path
export MODEL_DIR=/path/to/your/models
```

For detailed configuration options, see [PROJECT_GUIDE.md - Configuration](PROJECT_GUIDE.md#-configuration)

---

## 📚 Documentation

### Main Documentation

- **[README.md](README.md)** (this file) - Overview, quick start, basic usage
- **[PROJECT_GUIDE.md](PROJECT_GUIDE.md)** - Complete technical guide
  - Installation
  - Model training
  - Configuration
  - Development
  - Deployment
  - API reference
  - Troubleshooting
- **[CHANGELOG.md](CHANGELOG.md)** - Version history and changes

### Training Documentation

- **[training/guide.md](training/guide.md)** - Complete model training guide
  - Dataset requirements
  - Training configurations
  - Performance tuning
  - Advanced features

### Quick Links

| Topic | Documentation |
|-------|---------------|
| Installation | [Quick Start](#-quick-start) or [PROJECT_GUIDE.md](PROJECT_GUIDE.md#-installation) |
| Model Training | [training/guide.md](training/guide.md) |
| Deployment | [PROJECT_GUIDE.md - Deployment](PROJECT_GUIDE.md#-deployment) |
| API Reference | [API Reference](#-api-reference) or [PROJECT_GUIDE.md](PROJECT_GUIDE.md#-api-reference) |
| Troubleshooting | [PROJECT_GUIDE.md - Troubleshooting](PROJECT_GUIDE.md#-troubleshooting) |
| Configuration | [Configuration](#-configuration) or [PROJECT_GUIDE.md](PROJECT_GUIDE.md#-configuration) |

---

## 🚀 Deployment

### Quick Deploy to Render

1. Push your code to GitHub
2. Connect repository to [Render](https://render.com)
3. Render auto-detects `render.yaml`
4. Set environment variables
5. Deploy!

### Other Platforms

- **Heroku**: Uses `Procfile`
- **Docker**: Create Dockerfile from PROJECT_GUIDE
- **AWS**: Elastic Beanstalk compatible
- **Digital Ocean**: App Platform ready

For detailed deployment instructions, see [PROJECT_GUIDE.md - Deployment](PROJECT_GUIDE.md#-deployment)

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Guidelines

- Follow PEP 8 style guide
- Add tests for new features
- Update documentation
- Keep commits focused and descriptive



---

## 🆘 Support

Need help? Here are your options:

- 📖 **Documentation**: Check [PROJECT_GUIDE.md](PROJECT_GUIDE.md) for detailed guides
- 🎓 **Training Help**: See [training/guide.md](training/guide.md) for model training
- 🐛 **Issues**: [Open an issue](https://github.com/yourusername/movie-recommendation-system/issues) on GitHub
- 💬 **Discussions**: [GitHub Discussions](https://github.com/yourusername/movie-recommendation-system/discussions)

---

## 🎯 Roadmap

### Version 2.1 (Planned)
- [ ] User authentication system
- [ ] Personal watchlists
- [ ] Movie rating system
- [ ] Advanced filtering (multiple genres, year ranges)
- [ ] Recommendation history

### Version 2.2 (Planned)
- [ ] Collaborative filtering
- [ ] Social features (sharing, comments)
- [ ] Movie reviews
- [ ] Advanced analytics dashboard

### Version 3.0 (Long-term)
- [ ] Mobile applications (iOS/Android)
- [ ] Real-time recommendations
- [ ] Streaming service integration
- [ ] Enhanced ML models (hybrid recommendations)

---

## 📊 Performance

| Metric | Value |
|--------|-------|
| Recommendation Time | < 50ms |
| Search Response | < 100ms |
| Page Load | < 200ms |
| Memory Usage | ~200MB (100K movies) |
| Concurrent Users | 1000+ |
| Model Size | 180MB (100K movies) |

---

## 🙏 Acknowledgments

- Movie data from TMDB and IMDb
- Built with Django, scikit-learn, pandas
- UI inspired by modern design principles
- Community contributions and feedback

---

<div align="center">

**Made with ❤️ for movie lovers and developers**

[⭐ Star this repo](https://github.com/yourusername/movie-recommendation-system) •
[🐛 Report Bug](https://github.com/yourusername/movie-recommendation-system/issues) •
[💡 Request Feature](https://github.com/yourusername/movie-recommendation-system/issues)

</div>

---

## Enhanced Documentation - Learning Review

### Project Overview

This project is a Django-based movie recommendation web application. The web layer loads recommendation artifacts in the background, supports movie search/autocomplete, and returns content-based recommendations. The training pipeline builds a text "soup" from TMDB-style metadata, vectorizes it with TF-IDF, optionally applies TruncatedSVD, computes cosine similarity, and saves the artifacts needed for inference.


### Technologies Used

- Python
- Django
- Django REST Framework
- Pandas
- NumPy
- SciPy
- scikit-learn
- NLTK
- SQLite
- WhiteNoise
- Gunicorn

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
```

### Usage

```bash
python manage.py runserver
```

Then open `http://127.0.0.1:8000`.

For custom training, review `training/guide.md` and run `training/train.py` after placing the expected TMDB-style CSV dataset in the configured path.

### Folder Structure

```text
Movie-Recommendation-System-project_5/
|   .gitignore
|   CHANGELOG.md
|   db.sqlite3
|   LICENSE
|   manage.py
|   Procfile
|   PROJECT_GUIDE.md
|   README.md
|   render.yaml
|   requirements.txt
|
+---.github
|       FUNDING.yml
|
+---assets
|   +---demo-video
|   |       Application-Demo.gif
|   |       Application-Demo.mp4
|   |
|   \---images-for-readme
|           Architecture.png
|           Header.png
|           Homepage.png
|           Loading.png
|           Logo.png
|           Results.png
|
+---movie_recommendation
|       asgi.py
|       settings.py
|       urls.py
|       wsgi.py
|       __init__.py
|
+---recommender
|   |   admin.py
|   |   apps.py
|   |   models.py
|   |   tests.py
|   |   urls.py
|   |   views.py
|   |   __init__.py
|   |
|   +---migrations
|   |   |   __init__.py
|   |   |
|   |   \---__pycache__
|   |           __init__.cpython-39.pyc
|   |
|   \---templates
|       \---recommender
|               error.html
|               index.html
|               result.html
|
+---static
|       logo.ico
|
\---training
        guide.md
        infer.py
        train.py
```

### Workflow

1. `training/train.py` loads a TMDB-style CSV file.
2. The trainer filters movies, parses metadata columns, engineers text features, builds a TF-IDF matrix, optionally reduces dimensions, and computes similarity.
3. Model artifacts are saved as parquet, JSON, NumPy/NPZ, and pickle files.
4. Django loads those artifacts from `MODEL_DIR` in a background thread.
5. User searches for a movie in the browser.
6. The recommender finds the closest title and returns the most similar movies.

### Dataset Information

- The training code expects a TMDB-style movie dataset such as `TMDB_movie_dataset_v11.csv` or `TMDB  IMDB Movies Dataset.csv`.
- The large source dataset is not present in this repository snapshot.
- `db.sqlite3` is present for the Django app, but it is not the recommender training dataset.

### Model Information

- Algorithm: content-based filtering.
- Feature extraction: TF-IDF over combined metadata text.
- Similarity: cosine similarity.
- Optional dimensionality reduction: TruncatedSVD.
- Runtime artifacts expected by `recommender/views.py`: `movie_metadata.parquet`, `similarity_matrix.npz` or `similarity_matrix.npy`, `title_to_idx.json`, and `config.json`.
- These runtime artifacts were not found in the inspected project tree, so the app may require training or artifact placement before recommendations work.

### Important Files Verified

- `requirements.txt`: present
- `manage.py`: present
- `recommender/views.py`: present
- `movie_recommendation/settings.py`: present
- `training/train.py`: present
- `training/infer.py`: present
- `training/guide.md`: present
- `templates/`: present
- `static/`: present
- `LICENSE`: present

### Future Improvements

- Include a small demo model artifact set or document exactly where to download it.
- Add a startup check that clearly explains missing model files.
- Add tests for search, recommendation, and health endpoints.
- Move large generated files out of source control where appropriate.

### Learning Notes

- This project shows how recommender systems need both model-building code and careful runtime artifact management.
- Background loading improves user experience for large similarity matrices.
- Content-based recommenders are interpretable but depend heavily on the quality of metadata fields.

### Credits

- Original implementation belongs to its respective author(s).
- Documentation enhanced for educational review and learning.

### License

This project includes an MIT License.
