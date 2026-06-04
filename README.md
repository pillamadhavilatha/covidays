# 🦠 COVID-19 Global Data Analysis — Data Analyst Internship Project

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualisation-11557c)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
![Data Source](https://img.shields.io/badge/Data-Johns%20Hopkins%20CSSE-blue)

> **Internship Project** | Data Analytics | Time-Series Analysis | Python

---

## 📌 Project Overview

This project performs a comprehensive **Exploratory Data Analysis (EDA)** on the
**Johns Hopkins University CSSE COVID-19 dataset** — one of the most widely referenced
pandemic datasets in the world.

The analysis covers global confirmed case trends, country-level comparisons, daily new
case patterns, wave identification, and regional disparity — providing actionable insights
for public health decision-making.

---

## 🎯 Objectives

- Track the global spread of COVID-19 over time using time-series analysis
- Identify the top 10 most affected countries by confirmed case count
- Visualise daily new case trends and detect pandemic waves
- Compare outbreak trajectories across the top 5 nations
- Drill into India-specific trends as a regional case study
- Highlight global inequality in pandemic impact through a heatmap

---

## 📁 Repository Structure

```
covid-data-analysis/
│
├── notebooks/
│   └── COVIDDataAnalysis.ipynb        # Main analysis notebook (fully documented)
│
├── src/
│   └── data_loader.py                 # Reusable data loading & preprocessing utilities
│
├── outputs/
│   ├── global_confirmed_trend.png
│   ├── top10_countries_bar.png
│   ├── top15_heatmap.png
│   ├── india_trend.png
│   ├── daily_new_cases.png
│   └── top5_comparison.png
│
├── data/
│   └── README.md                      # Dataset info (auto-fetched from JHU GitHub)
│
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

---

## 📊 Dataset

| Property | Detail |
|----------|--------|
| **Source** | [Johns Hopkins University CSSE](https://github.com/CSSEGISandData/COVID-19) |
| **Type** | Live CSV fetched via URL (no manual download needed) |
| **Coverage** | Global — 180+ countries from Jan 2020 to Mar 2023 |
| **Format** | Wide-format time series — one column per date |
| **Target** | `Confirmed Cases` per country per date |

### Column Overview

| Column | Description |
|--------|-------------|
| `Province/State` | Sub-national region (often blank) |
| `Country/Region` | Country name |
| `Lat`, `Long` | Geographic coordinates |
| `1/22/20` … `3/9/23` | Cumulative confirmed cases per date |

> ✅ **No manual download required.** The notebook fetches data directly from the JHU GitHub repository at runtime.

---

## 🔍 Analysis Workflow

### 1️⃣ Data Ingestion
- Loaded directly from JHU CSSE raw GitHub URL using `pd.read_csv()`
- Parsed date columns into `datetime` objects

### 2️⃣ Data Cleaning
- Filled missing `Province/State` with `'Unknown'`
- Imputed missing `Lat` / `Long` with column mean
- Validated zero remaining nulls after cleaning

### 3️⃣ Exploratory Data Analysis
| Chart | Insight |
|-------|---------|
| Global confirmed cases trend | Exponential growth, multiple wave pattern |
| Top 10 countries bar chart | US, India, France lead total cases |
| Top 15 heatmap | Extreme case concentration in handful of nations |
| India trend line | Steep Delta and Omicron waves visible |
| Daily new cases (global) | Clear wave cycles with peaks and troughs |
| Top 5 country comparison | Different wave timing and severity per country |

---

## 📈 Key Insights

### 1. Global Infection Trend
- Cases grew **exponentially** from early 2020 before showing wave-like patterns
- Multiple distinct waves visible — each followed by decline due to interventions or immunity

### 2. Most Affected Countries
The **US, India, France, Germany, Brazil, Japan, South Korea, Italy, UK, and Russia**
accumulated the highest total confirmed case counts globally.

### 3. Regional Trends
- Countries experienced peaks at **different times**, reflecting varied public health responses
- Population size, testing capacity, and policy decisions significantly influenced recorded case numbers

### 4. Daily New Cases
- Clear wave cycles emerged in the daily new case chart
- Sharp peaks followed by rapid declines correlate with lockdown enforcement and vaccination rollouts

### 5. Heatmap Findings
- A small number of countries account for the **majority of global cases**
- This concentration reflects unequal pandemic impact, reporting infrastructure, and population density

---

## 🧰 Tech Stack

| Library | Version | Purpose |
|---------|---------|---------|
| `pandas` | ≥ 1.3 | Data loading, reshaping, grouping |
| `numpy` | ≥ 1.21 | Numerical operations (diff, mean) |
| `matplotlib` | ≥ 3.4 | Line charts, trend plots |
| `seaborn` | ≥ 0.11 | Bar charts, heatmaps |
| `jupyter` | ≥ 1.0 | Interactive notebook environment |

---

## ⚙️ Setup & Installation

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/covid-data-analysis.git
cd covid-data-analysis
```

### 2. Create and activate a virtual environment

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch the notebook

```bash
jupyter notebook notebooks/COVIDDataAnalysis.ipynb
```

> **Note:** An active internet connection is required — data is fetched live from GitHub at runtime.

---

## 🗂️ How to Run

1. Open `notebooks/COVIDDataAnalysis.ipynb` in Jupyter
2. Run all cells: **Kernel → Restart & Run All**
3. Outputs (charts) are saved automatically to the `outputs/` folder
4. No dataset download needed — the notebook fetches it automatically

---

## 💡 Business / Public Health Recommendations

Based on this analysis:

- **Surge preparedness:** Daily new case charts show predictable wave patterns —
  health systems should pre-position resources ahead of anticipated peaks
- **Targeted intervention:** Top-10 country analysis identifies where global
  health investment has the highest impact
- **Surveillance investment:** Countries with lower reported cases may have
  under-reporting issues — improving testing infrastructure is critical
- **Policy timing:** Country comparison shows earlier interventions correlate
  with flatter curves — response speed is a key determinant of outcomes

---

## 🤝 Acknowledgements

- **Data Source:** Johns Hopkins University Center for Systems Science and Engineering (CSSE)
  [COVID-19 GitHub Repository](https://github.com/CSSEGISandData/COVID-19)
- Internship guidance and project framework provided by the Data Analytics team

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

*Developed as part of a Data Analyst Internship project.*
