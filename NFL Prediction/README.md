# 🏈 NFL Game Results Modeling Project

This project provides a complete workflow for importing, processing, and modeling NFL game data using the [`nfl_data_py`](https://pypi.org/project/nfl-data-py/) package.  
It includes a Jupyter Notebook (`NFL_TRAIN_nfl-data-py.ipynb`) that demonstrates the data preparation and model training steps, and an Excel dataset (`nfl_game_results_full_model.xlsx`) containing the cleaned and enriched results.

---

## 📂 Project Structure

```
├── NFL_TRAIN_nfl-data-py.ipynb      # Main notebook for data import, cleaning, feature engineering, and modeling
├── nfl_game_results_full_model.xlsx # Final processed dataset with game-level features and results
└── README.md                        # Project documentation
```

---

## ⚙️ Requirements

Before running the notebook, install the following dependencies:

```bash
pip install pandas numpy nfl_data_py matplotlib seaborn scikit-learn openpyxl
```

---

## 🧠 Workflow Overview

### 1. Data Import
The notebook uses `nfl_data_py` to import:
- **Schedules and results** via `import_schedules()`
- **Weekly stats** via `import_weekly_data()`
- Optional: **rosters, weather, and player information**

### 2. Data Cleaning
Functions in the notebook handle:
- Converting temperatures and wind speeds to numeric values  
- Filling missing values with means or zeros  
- Creating derived features such as:
  - `cold_game` → whether temperature < 40°F  
  - `windy` → whether wind speed > 15 mph  

### 3. Feature Engineering
Normalization and renaming of columns (e.g., `team_abbr` → `team`, `season_year` → `season`) ensure consistency across datasets.

### 4. Model Building (optional)
The notebook may include basic modeling examples such as:
- Predicting game outcomes  
- Assessing feature importance  
- Visualizing team performance trends  

### 5. Export Results
The final dataset is saved as:
```
nfl_game_results_full_model.xlsx
```
This file contains all relevant processed columns, ready for downstream analysis or visualization.

---

## 📊 Example Columns in Output File

| Column Name | Description |
|--------------|-------------|
| `game_id` | Unique ID for each game |
| `season` | NFL season year |
| `week` | Week number |
| `team` | Team abbreviation |
| `opponent` | Opponent team abbreviation |
| `score` | Team score |
| `opp_score` | Opponent score |
| `cold_game` | Binary flag if temp < 40°F |
| `windy` | Binary flag if wind > 15 mph |
| `game_type` | Regular/Postseason indicator |

---

## 🧾 Output Example

| game_id | season | week | team | opponent | score | opp_score | cold_game | windy |
|----------|---------|------|------|-----------|--------|------------|------------|--------|
| 2022_01_ARI_KC | 2022 | 1 | ARI | KC | 21 | 44 | 0 | 0 |
| 2022_02_BUF_MIA | 2022 | 2 | BUF | MIA | 17 | 21 | 0 | 1 |

---

## 🚀 Usage

Open the notebook in Jupyter or VS Code:

```bash
jupyter notebook NFL_TRAIN_nfl-data-py.ipynb
```

Run each cell sequentially to reproduce the dataset or modify the workflow for your own analysis.

---

## 🧩 Future Improvements

- Add player-level features (QB rating, rushing yards, etc.)
- Integrate advanced weather data from APIs
- Build predictive models for point spreads or win probabilities
- Automate weekly updates via `nfl_data_py`

---

## 🏁 Author

**Mohamed Naji**  
Data Analyst & Sports Modeling Enthusiast  

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).
