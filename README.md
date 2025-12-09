# 🏎️ Predicting Formula 1 Race Outcomes (2022-2025)

A Data Science + Machine Learning Project on Podium Probabilities, Finishing Positions & Points

This repository contains the full code, data pipelines, models, and simulations behind my Formula 1 prediction project. Using telemetry, qualifying performance, pit strategy variables, and weather indicators from the 2022–2024 seasons, we built a set of machine learning models capable of:

✅ Predicting podium probability (binary classification)

✅ Predicting finishing position (ranked regression)

✅ Predicting points scored (numerical regression)

✅ Running what-if simulations (e.g., “How would wind or temperature change podium chances?”)

The project blends sports analytics, ML modeling, and real-world engineering logic from F1 racing.


⸻

## 🏁 Project Highlights

1. Podium Classifier (Logistic Regression + Feature Engineering)
	•	Predicts the probability that a driver finishes top 3.
	•	Uses calibrated probabilities (Platt scaling) and an optimized decision threshold.
	•	Key insight: qualifying round reached and grid position dominate predictive performance.

2. Finishing Position Model (Random Forest / XGBoost / Ordinal Regression)
	•	Predicts continuous finishing scores and re-ranks drivers within each race.
	•	Models evaluated with MAE, RMSE, Spearman/Kendall correlations, and Top-k accuracy.
	•	Best performer for 2024 out-of-sample: Random Forest.

3. Points Prediction (Regression)
	•	Parallel modeling pipeline using the official FIA scoring system.
	•	Best performer: XGBoost, with strong correlation to true points earned.

4. Weather What-If Simulations
	•	Adjust weather variables such as wind, temperature, pressure, and precipitation to measure model sensitivity.
	•	Key insight:
	•	Low air pressure increases podium probability the most across drivers.
	•	Wind has mild effects, and precipitation does almost nothing in recent seasons.

5. Full Race Prediction Example: Australian GP 2025
	•	Predicts podium chances, finishing positions, and points for the entire grid.
	•	Used as an end-to-end evaluation of the modeling framework.

⸻
## 🏁 Methodology Summary

	•	Temporal splits (train on 2022–2024, test on later seasons).
	•	Preprocessing via:
	•	median imputation
	•	z-score normalization
	•	one-hot encoding for driver, constructor, circuit
	•	Classification metrics: ROC-AUC, F1, lift, confusion matrix
	•	Regression metrics: MAE, RMSE, R², Spearman & Kendall correlations
	•	Feature importance via Random Forest and SHAP values
	•	Model calibration for probability realism
	•	Scenario simulation engine for stress-testing weather variables

⸻

## 🏁 Key Findings
	•	Qualifying is king — it is by far the strongest determinant of podium probability.
	•	Race execution (pit efficiency, tire life) matters more than raw lap time.
	•	Weather barely affects outcomes in the recent era — except air pressure.
	•	Machine learning can capture race dynamics, but surprise moments still belong to racing.

⸻

## 🏁 Predictions & Interpretation

The repo includes:
	•	Predicted podium chances for the 2025 season
	•	Full predicted finishing orders
	•	Per-driver sensitivity charts from weather simulations

These predictions are probabilistic, not deterministic. Intended to explore patterns, not claim certainty.

⸻
## 🙌 Acknowledgments

Thanks to FastF1, Jolpica, and the incredible open-source contributors to scikit-learn, XGBoost, and SHAP.
Of course… thank you to F1 for giving us the most beautiful data-generating process on Earth. 

⸻
## 👥 Contributors
**Carolina Rios** — EDA, modeling, what-if simulations, predictions, and co-author of the Medium article

**Emma Trunnell** — Feature extraction, data consolidation, final data analysis, and co-author of the Medium article

**Maria-Laura Peña** — Limitations & future work

**Abhi Pandya** — Abstract & introduction

**Prem Badri** — Feature extraction
