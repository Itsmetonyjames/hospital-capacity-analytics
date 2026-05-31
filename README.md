# Hospital Capacity Analytics using Statistical Programming

End-to-end statistical analysis of hospital encounter data to support capacity planning, identify demand drivers, and predict 30-day readmission risk.

---

## Business Questions

> 1. *How do admissions, ED visits, bed-days, and length of stay vary over time?*
> 2. *Which service lines and diagnoses drive the most capacity pressure?*
> 3. *Is there meaningful seasonal variation — and does LOS actually change by month?*
> 4. *Can we predict which patients are at risk of readmission within 30 days?*

---

## Dataset

| Property | Detail |
|---|---|
| Source | Synthea — open-source synthetic healthcare encounter data |
| Unit | Individual patient encounters |
| Key fields | Encounter start/stop, encounter class, diagnosis, patient ID |
| Derived features | Length of Stay (LOS), 30-day readmission flag, monthly aggregations |

---

## Analysis Pipeline

| Stage | Method | Library |
|---|---|---|
| Data cleaning | Column standardisation, datetime parsing, LOS computation | Pandas |
| Exploratory analysis | Monthly trends, service line breakdown, diagnosis ranking | Pandas, Matplotlib, Seaborn |
| Seasonal analysis | Monthly bed-day patterns by diagnosis group | Seaborn |
| Patient journeys | 30-day readmission flagging via patient-level sequencing | Pandas |
| Seasonal decomposition | Trend / seasonal / residual separation | Statsmodels |
| Inferential testing | One-way ANOVA — LOS variation by month | Scipy |
| Regression | OLS — drivers of length of stay | Statsmodels |
| Predictive modelling | Logistic Regression — 30-day readmission risk | Scikit-learn |

---

## Key Findings

- **Bed-day utilisation is growing structurally** — inpatient services show sustained long-term growth beyond seasonal variation
- **Seasonal peaks are predictable** — specific diagnosis categories spike in particular months, enabling proactive staffing
- **LOS does not vary significantly by month** (ANOVA p > 0.05) — seasonal pressure comes from *volume increases*, not longer stays
- **Inpatient LOS is significantly longer** than ED and outpatient encounters (OLS regression)
- **Most readmissions occur within the first 7 days** post-discharge — immediate follow-up is the highest-impact intervention
- **Encounter class is the strongest readmission predictor** — service-line-specific follow-up protocols are warranted

---

## Operational Recommendations

| Finding | Action |
|---|---|
| Long-term bed-day growth | Plan structural capacity increases |
| Predictable seasonal peaks | Diagnosis-specific surge staffing plans |
| LOS stable across months | Focus seasonal planning on admission volume management |
| Early post-discharge readmissions | 48-72 hour follow-up calls for high-risk patients |
| Service line predicts readmission | Targeted discharge protocols by encounter type |

---

## Files

| File | Description |
|---|---|
| `Hospital_Capacity_Analytics_Portfolio.ipynb` | Full analysis notebook |
| `SP_Report_Clean.pdf` | Project report |

---

## How to Run

```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn
jupyter notebook Hospital_Capacity_Analytics_Portfolio.ipynb
```

---

## Tools Used

`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn` `Statsmodels` `Scikit-learn`

---

*Tony James — MSc Data Science, York St John University, London*  
[LinkedIn](https://linkedin.com/in/tony-james-4bba63195) | [GitHub](https://github.com/itsmetonyjames)
