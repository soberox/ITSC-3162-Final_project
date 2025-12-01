# FIFA Data Mining — Final Project (ITSC-3162)

✅ Final project for ITSC-3162 — a collaborative data-mining and machine learning analysis of FIFA player data.

---

## Project overview

This repository collects the work of multiple team members who analyzed the dataset `fifa_eda_stats.csv` and built several machine learning solutions:

- **Classification** — predicting player attributes (example: preferred foot)
- **Regression** — predicting player market value using linear models and XGBoost
- **Recommendation** — nearest-neighbors based player recommendation (cosine similarity / k-NN)

Each solution is contained in its own Jupyter notebook so you can inspect the exploratory data analysis (EDA), preprocessing steps, modeling code, and visualizations.

---

## Files & Notebooks

- `fifa_eda_stats.csv` — the dataset used across the notebooks (source link below)
- `FinalProject.ipynb` — linear-regression-style analysis (value predictions + EDA)
- `XGBoostRegressionProjectNotebook.ipynb` — XGBoost model to predict player value (field players only)
- `classifying-which-preferred-foot-is-most-likely.ipynb` — classification model predicting preferred foot (RandomForest)
- `Recommendation.ipynb` — recommendation system for fans (nearest neighbors + cosine similarity, PCA/t-SNE for visualization)

---

## Dataset

The dataset used in this project is included in this repository as `fifa_eda_stats.csv` and originally comes from Kaggle:

https://www.kaggle.com/datasets/mukeshmanral/fifa-data-for-eda-and-stats

Please make sure to review and comply with the dataset's license/terms on Kaggle before reuse.

---

## How to run the notebooks (local)

1. Install Python 3.10+ (3.11 recommended) and create a virtual environment:

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

2. Install recommended packages (example):

```powershell
pip install --upgrade pip
pip install jupyterlab pandas numpy matplotlib seaborn scikit-learn xgboost scipy
```

3. Start Jupyter Lab / Notebook from the project root and open the notebooks:

```powershell
jupyter lab
# or
jupyter notebook
```

Notes:
- Each notebook contains the code cells required to reproduce the analyses. The notebooks also include small helper functions for parsing monetary values, heights, and weights used during preprocessing.
- If a notebook expects the dataset from a Kaggle path (e.g., a Kaggle kernel), change the read path to `./fifa_eda_stats.csv` when running locally.

---

## Quick descriptions (per notebook)

- `FinalProject.ipynb` — Author: Dokja
  - Performed EDA and a Linear Regression approach for predicting player `Value` (converts monetary values to numeric, filters numeric features, trains and evaluates a LinearRegression model). Visual: correlation heatmap, coefficient analysis.

- `XGBoostRegressionProjectNotebook.ipynb` — Author: JonathanC12 (commits from `jonat` / `JonathanC12`)
  - Focused on predicting player `Value` using XGBoost. Preprocessing filters out goalkeepers, drops non-informative columns and handles missing values, then trains an XGBoost regressor and reports RMSE / r2 score.

- `classifying-which-preferred-foot-is-most-likely.ipynb` — Classification notebook
  - Predicts whether a player prefers the left or right foot using a Random Forest Classifier. Includes preprocessing (money parsing, imputing missing values), model training and evaluation (confusion matrix, classification report, feature importances).

- `Recommendation.ipynb` — Recommendation notebook
  - Builds a player recommendation system for fans using feature standardization, dimensionality reduction (PCA / t-SNE), and NearestNeighbors with cosine similarity.

---

## Contributors (git authors)

Thanks to everyone that contributed. The commit history shows the following authors (as recorded in git):

- brawl7787 (soberox)
- RoadLamp (Streetlight321)
- Dokja (TheOldestDreamer)
- JonathanC12 (jonathan)

If you provided work in one of the notebooks but don't see your preferred name above, feel free to update the README or open a PR with the correct credit.

---

## Suggestions / next steps

- Add a `requirements.txt` or `environment.yml` to make environment setup reproducible.
- Convert notebooks into modular Python scripts for easier testing / CI.
- Add unit tests or small scripts that run the model pipeline end-to-end with sample data.

---

## License

This repository does not currently include an explicit license. If you want to publish this code publicly, consider adding a license (for example MIT, Apache-2.0) and add a `LICENSE` file.

---

If you want, I can also:

- add a `requirements.txt` listing exact dependencies and versions
- add a short `CONTRIBUTING.md` template (how to contribute and run notebooks)
- create an interactive README badge / binder link so others can run notebooks online

If you'd like any of those additions, tell me which and I’ll add them next. 🚀
