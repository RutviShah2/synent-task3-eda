# Netflix Dataset Analysis (synent_task3_eda)

This repository contains an exploratory data analysis (EDA) of the Netflix ``netflix_titles.csv`` dataset performed in the notebook ``synent_task3_eda.ipynb``.

## Project Overview

This project performs an initial exploratory analysis on Netflix titles to understand trends in content added over time, distributions of content types and ratings, and country-level contributions. The analysis includes data loading, cleaning, summary statistics, visualizations, and recommendations for further exploration.

## Notebook

- **Main notebook**: [synent_task3_eda.ipynb](synent_task3_eda.ipynb)

The notebook is organized into the following sections:
- 1. Load Data and Initial Exploration
- 2. Data Cleaning and Preparation
- 3. Summary Statistics
- 4. Trend Identification (Content Added Over Time)
- 5. Correlation Analysis
- 6. Next Steps / Further Exploration

## Dataset

- Filename expected: `netflix_titles.csv`
- Place the CSV in the same directory as the notebook, or update the path inside the notebook before running.
- Common public source: the Kaggle dataset "Netflix Movies and TV Shows" (if you do not already have the CSV).

Key columns used in the analysis:
- `type` — Movie or TV Show
- `title` — Title name
- `director` — Director(s)
- `cast` — Main cast
- `country` — Country of origin
- `date_added` — Date the title was added to Netflix
- `release_year` — Year the title was released
- `rating` — Content rating (PG, TV-MA, etc.)
- `duration` — Duration (minutes or number of seasons)
- `listed_in` / `genre` — Genre(s)

## Setup & Requirements

Recommended environment:
- Python 3.8 or newer
- Jupyter / JupyterLab or VS Code with the Jupyter extension

Minimal Python packages used in the notebook:
- `pandas`
- `matplotlib`
- `seaborn`

Install dependencies using pip (example):

```bash
python -m venv .venv
.\.venv\Scripts\activate     # Windows
pip install --upgrade pip
pip install pandas matplotlib seaborn jupyter
```

Alternatively create a `requirements.txt` with:

```
pandas
matplotlib
seaborn
jupyter
```

and install with `pip install -r requirements.txt`.

## How to run

1. Ensure `synent_task3_eda.ipynb` and `netflix_titles.csv` are in the same folder.
2. Start Jupyter Lab / Notebook or open the notebook in VS Code:

```bash
# From project root
jupyter lab
# or
jupyter notebook
```

3. Open the notebook and run cells top-to-bottom. The notebook prints helpful messages if the CSV is not found and will create an empty DataFrame in that case.

## What the notebook does (brief)

- Loads `netflix_titles.csv` into a pandas DataFrame (with error handling if file is missing).
- Converts `date_added` to datetime and extracts `year_added`.
- Fills missing values for `country` and `rating` (simple strategies: 'Unknown' and mode respectively).
- Drops rows with unparseable `date_added` values.
- Computes and displays summary statistics and value counts for `type`, `rating`, and `country`.
- Visualizes trends over time (titles added per year; movies vs TV shows), rating distribution by type, and top countries by content type.

## Expected outputs

- Summary tables: value counts, descriptive stats for `release_year` and `duration` (movies).
- Plots: line charts for content added by year; comparison line chart for movies vs TV shows; count plots for rating/type and country distributions.

## Reproducibility & Notes

- The notebook applies simple cleaning strategies; adapt imputation rules as needed for your analysis goals.
- Duration parsing in the notebook assumes a string format like `"90 min"` for movies.
- If you run this on a different variation of the dataset, check column names and types before running the full notebook.

## Suggested Next Steps

- Expand genre-level analysis using `listed_in` (tokenize and count genres).
- Perform NLP on the `description` column (topic modeling or TF-IDF) to surface themes.
- Compare Netflix acquisition (`year_added`) vs `release_year` to analyze licensing vs originals.
- Build dashboards (Streamlit / Dash) for interactive exploration.

## License & Contact

This repository does not include a license file. Add a `LICENSE` if you plan to share.
