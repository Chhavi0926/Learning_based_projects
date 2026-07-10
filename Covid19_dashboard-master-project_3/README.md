# COVID-19 Dashboard

## Project Overview
This dashboard visualizes COVID-19 data using Plotly Dash and presents global statistics through interactive charts and maps. It is useful for understanding how dashboards can turn live data into a clear analytical experience.

## Major Issues Observed
- The dashboard depends on external data sources, so it may be affected by availability or network issues.
- The project would benefit from stronger caching and a more polished deployment setup for production use.

## Features

- Interactive world map
- Live statistics
- Dynamic charts
- Responsive design
- Global data coverage
- Auto-updating

## Architecture

```
┌──────────────────────────┐
│   Plotly Dash Frontend   │
│  - Interactive Maps      │
│  - Charts & Statistics   │
│  - Real-time Updates     │
└────────┬─────────────────┘
         │
         ▼
┌──────────────────────────┐
│   Data Processing        │
│  - Pandas DataFrames     │
│  - Aggregation           │
│  - Transformations       │
└────────┬─────────────────┘
         │
         ▼
┌──────────────────────────┐
│   Data Sources           │
│  - JHU CSSE Data         │
│  - Global Health APIs    │
└──────────────────────────┘
```

## Project Files

- `covid19.py` - Main Dash application
- `requirements.txt` - Dependencies
- `assets/` - CSS styling
- `image/` - Dashboard screenshots

## Quick Start

```bash
# Create virtual environment
python -m venv venv

# Activate
# Windows: venv\Scripts\activate


# Install packages
pip install -r requirements.txt

# Run
python covid19.py
```

Open `http://127.0.0.1:8050` in your browser.

## Tech Stack

- Plotly Dash (dashboard framework)
- Pandas (data processing)
- Plotly (visualization)
- Bootstrap (UI framework)

✅ Data refreshes regularly with latest information

✅ Originally designed for Heroku deployment

✅ Mobile-responsive design

✅ Works without internet after initial setup (cached data)

---

## 🔗 Resources

- [Johns Hopkins COVID-19 Data](https://systems.jhu.edu)
- [Plotly Dash Documentation](https://dash.plotly.com)
- [Mapbox Maps](https://www.mapbox.com)


---

## Enhanced Documentation - Learning Review

### Project Overview

This project is a Plotly Dash dashboard for exploring global COVID-19 confirmed, recovered, and death counts. The main script downloads Johns Hopkins CSSE time-series CSV files, transforms them with Pandas, and renders maps, line charts, bar charts, summary cards, and a searchable data table.


### Features

- Global COVID-19 summary metrics.
- Interactive map using Plotly Mapbox configuration.
- Country-level table with selection-driven charts.
- Total and daily case visualizations.
- Heroku deployment files: `Procfile` and `runtime.txt`.
- Local CSS and dashboard images.

### Technologies Used

- Python
- Dash
- Plotly
- Pandas
- NumPy
- Gunicorn
- HTML/CSS assets

### Installation

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Usage

```bash
python covid19.py
```

Then open `http://127.0.0.1:8050`.

### Folder Structure

```text
Covid19_dashboard-master-project_3/
|   .gitignore
|   covid19.py
|   LICENSE
|   Procfile
|   README.md
|   requirements.txt
|   runtime.txt
|
+---assets
|       favicon.ico
|       test.css
|
\---image
        1_git.png
        2_git.png
        DarktoLightV2.gif
        Mapandbarchartanimation.gif
```

### Workflow

1. `covid19.py` reads confirmed, deaths, and recovered CSV files from the Johns Hopkins GitHub repository.
2. Pandas prepares aggregate totals, country totals, 24-hour changes, and map/table data.
3. Dash layouts define metric cards, chart areas, map, table, and modal content.
4. Dash callbacks update charts and map views based on selected controls and table rows.
5. Gunicorn can serve the app through `covid19:server` for deployment.

### Dataset Information

- Source used in code: Johns Hopkins CSSE COVID-19 time-series CSV files from GitHub.
- Local dataset files are not included.
- The app depends on network availability when loading remote CSV files.

### Model Information

- This is a data visualization/dashboard project, not a machine learning model training project.
- No model artifact is present or required.

### Important Files Verified

- `requirements.txt`: present
- `covid19.py`: present
- `Procfile`: present
- `runtime.txt`: present
- `assets/`: present
- `image/`: present
- `LICENSE`: present

### Future Improvements

- Add local caching or fallback CSV files for offline use.
- Update deprecated Dash imports to modern `dash.dcc`, `dash.html`, and `dash.dash_table` usage.
- Externalize the Mapbox token and optional scripts into environment variables.
- Add clear setup notes for deployments that block remote CSV access.

### Learning Notes

- The project is a strong example of turning public time-series data into interactive dashboard components.
- Dash callbacks are the core mechanism for connecting user actions to updated visualizations.
- Remote datasets make dashboards easier to update but more fragile without caching.

### Credits

- Original author referenced in the MIT License: Unicorndy.
- COVID-19 data source referenced in code: Johns Hopkins CSSE.
- Documentation enhanced for educational review and learning.

### License

This project includes an MIT License. 