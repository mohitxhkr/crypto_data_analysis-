# Data Science Assignment

**Author:** Mohit Kumar Gupta  
**Submission Date:** 2025-09-10  

---

## 📂 Project Structure

ds_MohitKumarGupta/
├── notebook_1.ipynb # Main Colab notebook (this file)
├── csv_files/ # Contains input & processed CSV files
│ ├── trader_data.csv # Raw historical trader data (input)
│ ├── fear_greed.csv # Market sentiment (input)
│ ├── daily_metrics.csv # Aggregated trader features (output)
│ └── merged_daily_with_sentiment.csv # Trader features + sentiment (output)
├── outputs/ # Visualization outputs
│ ├── boxplot_pnl_by_sentiment.png
│ └── hist_leverage_by_sentiment.png
├── ds_report.pdf # Final PDF report (root level, required)
└── README.md # Project documentation

markdown
Copy code

---

## 🚀 How to Run

1. **Open in Google Colab**
   - Upload the folder to your Google Drive or open directly via Colab.

2. **Install dependencies**
   - The notebook installs required packages:
     ```python
     !pip install -q gdown pandas numpy matplotlib seaborn scikit-learn scipy
     ```

3. **Get the datasets**
   - By default, the notebook downloads:
     - `trader_data.csv`
     - `fear_greed.csv`
   - If the Google Drive links fail (permissions), upload the CSVs manually to the `csv_files/` folder.

4. **Run all cells (top to bottom)**
   - Produces aggregated metrics, sentiment merge, visualizations, ML baseline, and the final PDF.

---

## 📊 Workflow Summary

1. **Data Loading & Cleaning**
   - Robust handling of `time` / `Timestamp` column → parsed to `date`.
   - Normalizes fields (`size`, `closedPnL`, `side`, etc.).

2. **Feature Engineering**
   - Daily metrics: trade counts, volumes, win rates, leverage, long/short mix.
   - Exported to `csv_files/daily_metrics.csv`.

3. **Sentiment Integration**
   - Joined with Fear & Greed Index (`classification` column).
   - Exported to `csv_files/merged_daily_with_sentiment.csv`.

4. **Exploratory Data Analysis**
   - Boxplot: Average ClosedPnL by sentiment.
   - Histogram: Leverage distribution by sentiment.
   - Welch’s t-test to compare `Fear` vs `Greed`.

5. **Machine Learning Baseline**
   - RandomForest Classifier predicts **next-day sentiment**.
   - Uses **lag features** (to avoid leakage) + **time-based split** (80/20).
   - `class_weight="balanced"` handles class imbalance.

6. **Final Report**
   - `ds_report.pdf` generated at **project root**.
   - Includes summary stats + visualizations.

---

## ✅ Key Strengths

- **Robust Date Handling:** Works whether trader data has `time` or `Timestamp`.
- **Leakage-Free ML:** Uses lag features and chronological split.
- **Balanced Evaluation:** Guards for class imbalance and insufficient sample sizes.
- **Evaluator Compliance:** Final report (`ds_report.pdf`) at root; correct folder structure.

---

## 📌 Notes

- If gdown fails due to access restrictions, upload the CSVs manually.
- Visualizations are optional but recommended for richer PDF output.
- Additional exploration can be added in a separate `notebook_2.ipynb`.

---

## 🏆 Deliverables

- **Notebook:** `notebook_1.ipynb` (Colab-compatible)
- **CSV Outputs:** Daily metrics + merged sentiment
- **Visualizations:** Stored in `outputs/`
- **Report:** `ds_report.pdf` at project root (submission requirement)

---
