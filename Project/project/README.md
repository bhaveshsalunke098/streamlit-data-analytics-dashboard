# 📊 Lucid — Analytics Studio

A production-ready, portfolio-worthy Streamlit web application for uploading,
cleaning, analyzing, visualizing, and generating business insights from any
CSV or Excel dataset — no code required from the end user.

Built with **Python, Streamlit, Pandas, NumPy, Plotly, Scikit-learn, OpenPyXL,
ReportLab,** and **SciPy**.

---

## ✨ Features

- **File Upload** — CSV and Excel (.xlsx, .xls), with instant file summary.
- **Automatic Data Cleaning** — deduplication, missing-value handling, text
  normalization, column-name standardization, and smart type detection in one click.
- **Manual Cleaning Tools** — drop/fill NA, remove duplicates, rename/delete
  columns, convert data types.
- **Data Profiling** — shape, dtypes, missing-value report, statistical summary,
  categorical breakdowns.
- **Data Quality Scoring** — a composite 0–100 score across completeness,
  uniqueness, validity, and consistency, plus a plain-English issues list.
- **Exploratory Data Analysis** — numerical and categorical statistics.
- **Advanced Analytics** — trend analysis (MoM/YoY growth), correlation
  analysis, and outlier detection (IQR & Z-score methods).
- **Interactive Visualizations** — bar, line, pie, histogram, box, scatter,
  and correlation heatmaps, built with Plotly.
- **Smart Chart Recommendation Engine** — pick one or two columns and get the
  best chart type with a plain-English reason.
- **Natural Language Query** — type questions like *"top 10 products"* or
  *"revenue trend"* and get an instant chart.
- **AI-Powered Business Insights** — best-performing segments, regional
  breakdowns, growth/seasonal trends, correlation insights, and outlier
  alerts, written in business language when business-style columns are
  detected (revenue, region, product, date), or plain statistical language
  otherwise.
- **Automated Data Storytelling** — executive summary, key findings, and
  recommendations generated directly from your data.
- **Machine Learning Module** — Linear Regression and Random Forest models
  against any numeric target, with R²/MAE/RMSE, feature importance, and
  forward projections.
- **Exports** — cleaned CSV/Excel, and PDF reports for Data Quality,
  Analytics, and Business Insights.
- **Bonus Tools** — dataset comparison, correlation alerts, smart data
  recommendations, and a one-click full-analysis pipeline.
- **Modern UI** — sidebar navigation, light/dark mode, KPI dashboard cards.

---

## 📁 Project Structure

```
project/
│
├── app.py                     # Main entry point, navigation, theming
│
├── pages/
│   ├── home.py                # Landing page
│   ├── upload.py               # File upload
│   ├── cleaning.py             # Automatic + manual cleaning
│   ├── profiling.py            # Data profiling
│   ├── quality.py              # Data quality scoring + alerts
│   ├── analytics.py            # EDA, trends, correlation, outliers
│   ├── visualization.py        # Chart builder, smart recs, NL query
│   ├── insights.py              # AI insights + data storytelling
│   ├── ml.py                    # Machine learning module
│   └── reports.py               # Exports + dataset comparison
│
├── utils/
│   ├── cleaner.py               # Cleaning pipeline + manual ops
│   ├── profiler.py              # Profiling, quality scoring, column roles
│   ├── visualizer.py            # Plotly chart builders + chart recommender
│   ├── insights_engine.py       # Business insights + storytelling
│   ├── ml_engine.py             # Regression models + predictions
│   ├── report_generator.py      # PDF report generation + exports
│   └── ui_helpers.py            # Shared UI components
│
├── assets/                      # Sample data / static assets
├── reports/                      # (scratch space for generated reports)
├── requirements.txt
├── README.md
└── .streamlit/
    └── config.toml               # Theme + server config
```

---

## 🚀 Installation Guide

### 1. Clone or download the project

```bash
git clone <your-repo-url>
cd project
```

### 2. Create a virtual environment (recommended)

```bash
python3 -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the app

```bash
streamlit run app.py
```

The app will open automatically in your browser at `http://localhost:8501`.

---

## ☁️ Deployment Guide — Streamlit Community Cloud

1. Push this project to a public (or private, with appropriate access) GitHub
   repository, including `app.py`, `pages/`, `utils/`, and `requirements.txt`.
2. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub.
3. Click **New app**, select your repository and branch, and set the main
   file path to `app.py`.
4. Click **Deploy**. Streamlit Cloud will install everything from
   `requirements.txt` automatically.
5. Your app will be live at a public `*.streamlit.app` URL within a few minutes.

### Notes for deployment
- No API keys or secrets are required — the entire app runs locally on
  whatever machine hosts it, with no external network calls.
- If you hit a memory limit on very large files, consider adding a file-size
  cap in `pages/upload.py`.
- To customize the theme colors, edit `.streamlit/config.toml`.

---

## 🧪 How the "AI" Works

This app does **not** call an external LLM API. The "AI-powered" insights and
data storytelling are generated by a structured rule-based engine
(`utils/insights_engine.py`) that:

1. Detects column **roles** (numeric, categorical, datetime) and **semantic
   tags** (revenue-like, region-like, product-like, customer-like, date-like)
   purely from column names and data shape — no hardcoded dataset assumptions.
2. Applies statistical heuristics (group-by aggregations, period-over-period
   growth, correlation thresholds, IQR outlier detection) to the data.
3. Converts the results into natural-language insights, adapting vocabulary:
   **business language** (e.g. "top-performing segment") when business-style
   columns are detected, or **neutral statistical language** otherwise.

This makes the app fully **offline-capable** and free to run with no API costs.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Web framework | Streamlit |
| Data manipulation | Pandas, NumPy |
| Visualization | Plotly |
| Machine learning | Scikit-learn |
| Excel I/O | OpenPyXL, XlsxWriter |
| PDF generation | ReportLab |
| Statistics | SciPy |

---

## 📄 License

This project is provided as a portfolio/demonstration template. Feel free to
fork, modify, and use it as the foundation for your own data analytics tools.
