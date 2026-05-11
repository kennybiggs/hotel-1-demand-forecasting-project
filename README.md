# Hotel Demand Forecasting Project

## Overview
This project forecasts daily room demand for 17 hotel properties 
over a 28-day horizon using a suite of statistical, machine learning, 
and neural forecasting models.

**Forecast horizon:** h = 28 days  
**Number of series:** 17 hotels  
**Cross-validation:** 5-fold, non-overlapping, step_size = 28

---

## Models Compared
| Category | Model |
|---|---|
| Baseline | Naive, Seasonal Naive |
| Statistical | AutoETS, AutoARIMA |
| Machine Learning | LightGBM (via MLForecast) |
| Neural | NBEATS, NHITS (via NeuralForecast) |

---

## Evaluation Metrics
- ME (bias)
- MAE
- RMSE
- MAPE (where appropriate)

---

## Key Findings
_Fill this in based on your win counts table from Cell 18 and 23._

Example: "SeasonalNaive won the most series on MAE during cross-validation, 
suggesting strong weekly seasonality across properties. LightGBM performed 
best on RMSE for higher-demand hotels. NBEATS and NHITS were competitive 
but showed instability on near-zero demand series (hotel_28, hotel_77)."

---

## Files
| File | Description |
|---|---|
| `ISA_444_Final_Project.ipynb` | Full modeling pipeline |
| `outputs/evaluation_all_models.csv` | CV evaluation by model and series |
| `outputs/cv_model_win_counts.csv` | CV model win counts |
| `outputs/final_test_evaluation.csv` | Test set evaluation |
| `outputs/final_model_win_counts.csv` | Test model win counts |
| `outputs/final_forecasts_all_models.csv` | Final forecasts for all models |

---

## Forecast Plots
Plots for all 17 hotels are in the `/plots` folder.

---

## Notes
- hotel_28 and hotel_77 are near-zero demand series. MAPE is not 
  reported for these as it is undefined/unreliable at near-zero values.
- NBEATS and NHITS were run with fixed hyperparameters (max_steps=100) 
  rather than auto-tuning due to computational constraints.
