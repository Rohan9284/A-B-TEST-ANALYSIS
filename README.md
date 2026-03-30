# A-B-TEST-ANALYSIS

 A/B Test Business Analysis

 1) Purpose
Evaluate whether a new website variant improves conversion rate compared to the control and provide a go/no-go recommendation.

 2) Experiment Design
- **Population split:** Control (original page) vs Variant (new page)
- **Primary metric:** Conversion Rate = % of users with `REVENUE > 0`
- **Statistical test:** Two-proportion Z-test

 3) Tech Stack
- Python
- pandas (data prep), statsmodels (stats), seaborn/matplotlib (viz), pandasql (SQL-style queries)

 4) Data Preparation
- **Duplicate removal:** Enforced unique user IDs to prevent repeat counting.
- **Feature engineering:** Added boolean `converted` flag for paying vs non-paying users.

 5) Results (Z-Test)
- Control conversion ≈ **1.50%**
- Variant conversion ≈ **1.35%**
- P-value = **0.6063**

 6) Interpretation
- No statistically significant lift (p-value ≫ 0.05).
- Observed difference is likely random noise.
- **Recommendation:** Fail to reject the null; do **not** roll out the variant. Explore other design/feature changes to drive conversion.

 7) Reproducing the Analysis
1. Place `AB_Test_Results.csv` in the project root.
2. Install dependencies:
   ```bash
   pip install pandas statsmodels seaborn matplotlib pandasql
   ```
3. Run the notebook:
   ```bash
   jupyter notebook AB_Testing_Business_Analysis.ipynb
   ```

 8) Repository Structure
- `AB_Testing_Business_Analysis.ipynb` — main analysis notebook
- `AB_Test_Results.csv` — input dataset (not tracked)
- `README.md` — project documentation
