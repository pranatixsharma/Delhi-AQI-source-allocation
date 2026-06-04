# Delhi AQI Decoded

A machine learning study of ambient air pollution across the Delhi National Capital Region (2020–2025), covering 23 CPCB monitoring stations and 201,664 observations. The project addresses three research questions: spatial clustering of station pollution profiles, quantification of policy interventions (COVID-19 lockdown, stubble burning, wind dispersion), and attribution of AQI variance to meteorological versus anthropogenic drivers.

---

## Research Questions

1. **Spatial profiling** — Do Delhi NCR monitoring stations fall into structurally distinct pollution clusters, and what emission sources drive each cluster?
2. **Policy impact** — How much did the COVID-19 lockdown reduce PM2.5? What would eliminating stubble burning or increasing wind dispersion achieve?
3. **Attribution** — What proportion of AQI variability is explained by meteorology versus human activity?

---

## Dataset

- **Source:** Central Pollution Control Board (CPCB), India
- **Coverage:** 23 stations across Delhi, Ghaziabad, Faridabad, Gurugram, Noida
- **Period:** January 2020 – December 2025
- **Observations:** 201,664 (4 snapshots/day: 06:00, 12:00, 18:00, 23:00 IST)
- **Features:** PM2.5, PM10, NO₂, SO₂, CO, O₃, temperature, humidity, wind speed, visibility, AQI

---

## Methods

| Step | Technique |
|------|-----------|
| Exploratory analysis | Seasonal decomposition, diurnal profiling, station ranking |
| Feature engineering | Cyclical encodings, event flags (lockdown, Diwali, stubble season), station clustering |
| Station clustering | K-means (k=3) on median pollutant profiles, silhouette validation |
| Predictive modelling | Linear Regression, Random Forest, XGBoost, SVR, ANN (MLP) |
| Interpretability | SHAP TreeExplainer, group-level attribution, cluster-wise decomposition |
| Counterfactual analysis | Model-based scenario simulation (stubble ban, wind increase, lockdown) |

---

## Key Results

- **Random Forest** achieved the best PM2.5 prediction: R² = 0.992, RMSE = 16.76 µg/m³, MAE = 8.84 µg/m³
- **Three station clusters** identified: *clean* (10 stations), *mixed urban* (8), *high emission* (5 — including Anand Vihar, Bawana, Jahangirpuri)
- **COVID-19 lockdown** reduced observed PM2.5 by 100.4 µg/m³ (53.7%)
- **Weather-only models** explain ~89% of AQI variance (R² = 0.889–0.891)
- **Full-model SHAP**: co-pollutants account for 67.7% of explained PM2.5 variance, temporal/human activity 29.6%, meteorology only 1.5%

---

## Repository Structure
├── Copy_of_DELHI_AQI_DECODED.ipynb   # Main analysis notebook (with outputs)
├── delhi_ncr_aqi_dataset.csv          # Dataset
└── README.md

---

## Requirements
python >= 3.9
pandas
numpy
scikit-learn
xgboost
shap
matplotlib
seaborn

Install dependencies:

```bash
pip install pandas numpy scikit-learn xgboost shap matplotlib seaborn
```


---

## Authors

Rupashi  Maurya
Pranati Sharma


---

## License

This project is for academic research purposes.
