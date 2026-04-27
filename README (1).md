# 🌍 Global Terrorism Exploratory Data Analysis (1970–2017)

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Libraries](https://img.shields.io/badge/Libraries-Pandas%20%7C%20NumPy%20%7C%20Matplotlib%20%7C%20Seaborn-green)
![Type](https://img.shields.io/badge/Project%20Type-EDA-purple)

## 📌 Project Overview

This project performs a comprehensive **Exploratory Data Analysis (EDA)** on the **United Nations Global Terrorism Analysis (UNGTA)** dataset, which records over **180,000 terrorist incidents** from **1970 to 2017** across the globe.

The goal is to extract meaningful insights about terrorism trends, hotspots, methods, and groups — insights that are directly useful to governments, security agencies, humanitarian organizations, and policy makers.

---

## 🎯 Business Objective

To analyze global terrorism data and answer:
- How has global terrorism evolved over 47 years?
- Which countries and regions are the most affected?
- What attack types and weapons cause the most casualties?
- Which terrorist groups are the most dangerous?
- What patterns exist in timing, targets, and tactics?

---

## 📂 Project Structure

```
global-terrorism-eda/
│
├── Global_Terrorism_EDA.ipynb   ← Main analysis notebook (21 charts)
├── README.md                    ← This file
└── globalterrorismdb_0718dist.csv  ← Dataset (download separately, see below)
```

---

## 📊 Dataset

- **Source:** Global Terrorism Database (GTD) — maintained by the National Consortium for the Study of Terrorism and Responses to Terrorism (START), University of Maryland.
- **Records:** ~180,000 terrorist incidents
- **Time Range:** 1970–2017
- **Key Columns Used:**

| Column | Description |
|--------|-------------|
| `iyear`, `imonth`, `iday` | Date of incident |
| `country_txt`, `region_txt`, `city` | Location |
| `attacktype1_txt` | Type of attack (bombing, armed assault, etc.) |
| `targtype1_txt` | Target type (civilians, military, government, etc.) |
| `gname` | Name of terrorist group |
| `weaptype1_txt` | Weapon used |
| `nkill` | Number killed |
| `nwound` | Number wounded |
| `success`, `suicide` | Attack outcome flags |

> **Note:** The dataset file (~163 MB) is not included in this repo due to size limits. Download it from [Kaggle GTD Dataset](https://www.kaggle.com/datasets/START-UMD/gtd) and place it in the root folder.

---

## 🔍 Key Steps in the Notebook

1. **Data Loading** — Load and inspect 180,000+ records
2. **Data Cleaning** — Handle missing values (median imputation for numerical, 'Unknown' fill for categorical)
3. **Outlier Treatment** — IQR-based capping (Winsorization) preserving extreme events
4. **Feature Engineering** — `total_casualties`, `decade`, `is_lethal` columns
5. **Univariate Analysis** — Distributions of attacks, regions, attack types, targets
6. **Bivariate Analysis** — Casualties by attack type, region trends, group rankings
7. **Multivariate Analysis** — Heatmaps, pair plots, grouped bar charts
8. **Business Recommendations** — 7 evidence-based suggestions

---

## 📈 Visualizations (21 Charts)

| # | Chart | Type | Analysis |
|---|-------|------|----------|
| 1 | Attacks Per Year (1970–2017) | Line + Area | Univariate |
| 2 | Top 15 Countries by Attacks | Horizontal Bar | Univariate |
| 3 | Attack Type Distribution | Bar | Univariate |
| 4 | Target Type Distribution | Bar | Univariate |
| 5 | Attacks by World Region | Pie | Univariate |
| 6 | Attacks Over Time by Region | Multi-Line | Bivariate |
| 7 | Avg Casualties by Attack Type | Bar | Bivariate (Num–Cat) |
| 8 | Top 15 Most Active Groups | Horizontal Bar | Bivariate |
| 9 | Monthly Attack Distribution | Bar | Bivariate |
| 10 | Attack Success Rate by Type | Bar | Bivariate (Num–Cat) |
| 11 | Total Casualties by Region | Bar | Bivariate (Num–Cat) |
| 12 | Killed vs. Wounded (Scatter) | Scatter | Bivariate (Num–Num) |
| 13 | Suicide vs Non-Suicide Attacks | Stacked Bar | Bivariate |
| 14 | Top 10 Groups by Casualties | Bar | Bivariate |
| 15 | Region vs Attack Type | Heatmap | Bivariate (Cat–Cat) |
| 16 | Decade-wise Attacks by Region | Grouped Bar | Multivariate |
| 17 | Top 10 Most Attacked Cities | Bar | Multivariate |
| 18 | Lethality Rate by Region | Bar | Multivariate |
| 19 | Casualties by Weapon Type | Box Plot | Multivariate |
| 20 | Correlation Heatmap | Heatmap | Multivariate |
| 21 | Pair Plot by Lethality | Pair Plot | Multivariate |

---

## 🔑 Key Findings

- 📈 Global terrorism **peaked in 2014–2015** (driven by ISIL's rise) and has declined since
- 🇮🇶 **Iraq, Pakistan, Afghanistan** are the most attacked countries; **Baghdad** the most attacked city
- 💣 **Bombing/Explosion** is the #1 attack method; **Chemical attacks** have the highest casualties per event
- 👥 **Private citizens** are the most frequent targets
- ☠️ **Taliban** (most attacks) and **ISIL** (most casualties) are the most dangerous groups
- 💥 **Suicide attacks** are rare but far more lethal than conventional attacks
- 🌍 **Sub-Saharan Africa** is a rapidly rising hotspot that demands urgent attention

---

## 🛠️ Libraries Used

```python
pandas       # Data manipulation and aggregation
numpy        # Numerical computations
matplotlib   # Base visualizations
seaborn      # Statistical visualizations
warnings     # Suppress non-critical warnings
```

---

## 🚀 How to Run

### Option A — Google Colab (Recommended for beginners)
1. Open [Google Colab](https://colab.research.google.com/)
2. Upload `Global_Terrorism_EDA.ipynb`
3. Upload the CSV dataset using the Files panel (left sidebar)
4. Run all cells: **Runtime → Run all**

### Option B — Local (Jupyter Notebook)
```bash
# 1. Clone this repository
git clone https://github.com/[your-username]/global-terrorism-eda.git
cd global-terrorism-eda

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Place the dataset CSV in this folder

# 4. Launch Jupyter
jupyter notebook Global_Terrorism_EDA.ipynb
```

---

## 👤 Author

**Manan Bhatt**   

---

## 📄 License

This project is for educational purposes as part of a Data Science course assignment.  
Dataset credit: National Consortium for the Study of Terrorism (START), University of Maryland.
