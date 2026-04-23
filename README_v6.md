# Interactive Regression Analysis - v6

This Streamlit app fits linear or polynomial regressions to either:
- **Group means**
- **Raw replicates**

and plots:
- **mean ± error**
- an overlaid **regression curve**
- optional **raw replicate points**
- the estimated **x_opt** from the fitted curve.

## Main updates in v5
- Removed the editable fields for **Experimental mean label** and **Regression curve label**.
- Default **Stats box font size** set to **9**.
- Added `?` help text to:
  - **Fit based on**
  - **Error bars shown on mean points**
  - **X-axis display**
- Moved **Interpretation help** into the **Results** area as a third column.
- Removed **Save plot to selected folder**.
- Moved **Download plot** next to the graph.
- Removed the **Save folder** field.

## Run
```bash
streamlit run streamlit_regression_dual_r2_v5.py
```

## Input Excel format
- Row 1: numeric concentrations
- Rows below: replicate values for each concentration

Example:
| 0 | 24 | 120 | 240 |
|---|---|---|---|
| rep1 | rep1 | rep1 | rep1 |
| rep2 | rep2 | rep2 | rep2 |

## Meaning of the R² values
- **R² (fit basis)**: calculated on the same data used for fitting.
- **R² (means)**: calculated on one mean per concentration.
- **R² (raw)**: calculated on all individual replicate values.

## Recommended use
- Use **ANOVA/post hoc** to decide which tested concentration is best statistically.
- Use the regression and **x_opt** as an interpolated estimate between tested concentrations.
- If fitting **Group means**, a common setup is:
  - show **SD** on the graph
  - use **SEM** as weights for the fit
