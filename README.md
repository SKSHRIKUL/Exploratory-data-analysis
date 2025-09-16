# Comprehensive Telecom Marketing Campaign Analysis (Assessment Task 1)

This project delivers a human-readable, end-to-end Exploratory Data Analysis (EDA) and visualization suite for a telecom marketing campaign dataset. It consolidates loading, preprocessing, segmentation insights, campaign strategy evaluation, timing analysis, financial/economic factors, and a comprehensive visualization dashboard, concluding with key findings and strategic recommendations.

## Project Goals
- Understand customer segments with higher subscription propensity
- Evaluate campaign execution factors (contacts, timing, channels)
- Examine financial/economic indicators in relation to outcomes
- Produce a comprehensive, presentation-ready dashboard and report

## Repository Structure
- `Telecom_Data_NoQuotes.csv`  
  Source dataset (semicolon `;` separated).
- `EDA.ipynb`  
  Main analysis notebook (EDA + Visualizations + Recommendations).
- `README.md`  
  You are here.

Note: If you recreated the notebook with a different name, update references accordingly.

## Data
- Rows: ~41k  
- Target: `y` (yes/no), mapped to numeric `subscribed` (1/0)  
- Key fields: `age`, `job`, `education`, `marital`, `contact`, `month`, `day_of_week`, `campaign`, `previous`, `pdays`, macro indicators (e.g., `euribor3m`, `cons.conf.idx`), and call `duration` (handle with leakage caution).

## Environment Setup
Recommended Python 3.8+.

Install dependencies:
```bash
pip install pandas matplotlib seaborn numpy
```

## Quickstart
1. Ensure the dataset file is present at the repo root: `Telecom_Data_NoQuotes.csv` (separator `;`).
2. Open the notebook `EDA.ipynb` in Jupyter:
```bash
jupyter notebook EDA.ipynb
```
3. Run all cells (Kernel → Restart & Run All).

## Notebook Workflow (What the analysis does)
1. Load & Preprocess
   - Read CSV with `sep=';'`
   - Map `y` → `subscribed` (1/0)
   - Create `age_group` buckets
   - Clean `pdays` (replace 999 with -1 as sentinel) and add `has_previous_contact`

2. Customer Segmentation
   - Subscription propensity by `job`, `age_group`, `education`, `marital`
   - Ranked rates with tabular summaries

3. Communication Channels
   - Compare `contact` methods (e.g., cellular vs telephone)

4. Campaign Timing
   - Monthly and day-of-week subscription rates
   - Identify high/low-performing windows

5. Campaign Contact Strategy
   - Subscription rate vs `campaign` contact count (first 10)
   - Effectiveness decline across contacts with percentage drop

6. Financial & Economic Factors
   - Housing/personal loan status vs subscription
   - Correlations with numeric macro indicators

7. Comprehensive Dashboard
   - 10-panel dashboard: segments, timing, channels, loans, summary table, and text insights

8. Key Findings & Recommendations
   - Target segments, optimal timing windows, contact strategy guidance, macro context

## Visualizations Included
- Bar charts: job, age group, education, loan status, monthly/weekly rates
- Line/Trend: subscription vs campaign contacts
- Comparative: communication channels
- Table: overall performance summary (color-coded)
- Advanced EDA (optional cells):
  - Correlation heatmap for numeric features
  - Distributions and box plots (outlier review)
  - Cross-tabulations for categorical variables

## EDA Techniques Applied
- Grouped rate calculations and ranking
- Feature engineering (`age_group`, `pdays_clean`, `has_previous_contact`)
- Correlation analysis (numeric → target)
- Distribution and outlier inspection
- Cross-tabulation (normalized) for categorical vs target

## Reproducibility & Notes
- Separator is `;` — ensure your editor preserves it when saving
- `duration` is outcome-dependent and can cause target leakage in predictive modeling; it is useful for EDA but should be excluded/handled with care in models
- Unknown categories (e.g., `unknown`, `nonexistent`) are retained to reflect operational uncertainty

## Troubleshooting
- Encoding/Parsing: If load fails, check file encoding and make sure `sep=';'` is used
- Missing Columns: Confirm the dataset schema matches the notebook expectations
- Visualization Backend: If plots don’t render, ensure you’re running inside a Jupyter environment

## Deliverables Checklist
- [x] Clean, human-readable notebook
- [x] EDA across segments, channels, timing, contacts
- [x] Dashboard with clear, professional visuals
- [x] Actionable findings & recommendations
- [x] Assessment Task 1 alignment

## License / Use
For academic use as part of Assessment Task 1 unless otherwise specified by your institution’s policy.

## Contact
If you need help running the notebook or tailoring the analysis:
- Maintainer: [Your Name]
- Email: [your.email@example.com]
