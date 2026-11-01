# AI-Powered Solar Energy Forecasting and Fault Detection

An intelligent solar energy monitoring and decision-support
prototype combining Electrical Engineering, Machine Learning,
Deep Learning, and statistical anomaly detection.

## Project Overview

This project analyzes solar power generation data from two plants.
It combines four forecasting models with two complementary
anomaly-detection approaches.

### Main Features

- Solar generation monitoring and plant comparison
- 15-minute-ahead AC power forecasting
- Linear Regression, Random Forest, XGBoost, and LSTM comparison
- Isolation Forest anomaly detection
- Engineering-based potential underperformance detection
- Combined alerts for observations flagged by both methods
- Interactive Streamlit dashboard
- CSV export of filtered monitoring results

## Model Evaluation

The models were evaluated on 1,278 common test observations.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 1287.25 | 2128.82 | 0.9047 |
| Random Forest | 1090.71 | 2151.62 | 0.9026 |
| XGBoost | 1107.55 | 2213.34 | 0.8969 |
| LSTM | 1376.86 | 2474.36 | 0.8712 |

Random Forest achieved the lowest MAE, while Linear Regression
achieved the best RMSE and R².

## Anomaly Detection

The project uses:

1. Isolation Forest to identify unusual daylight observations.
2. An engineering-based statistical method to identify
   potential underperformance relative to historical power output.
3. Combined detection to prioritize observations flagged by
   both methods.

An alert is an indication for investigation, not proof of
an equipment fault.

## Dataset

Dataset: Solar Power Generation Data

Source:
https://www.kaggle.com/datasets/anikannal/solar-power-generation-data

The dataset contains generation and weather observations
from two solar plants.

Check the original dataset's license and terms before
redistributing its data files.

## Project Structure

```text
solar_monitoring_dashboard/
│
├── app.py
├── requirements.txt
├── README.md
├── metadata.json
│
├── data/
│   ├── solar_data.csv
│   ├── forecast_results.csv
│   ├── model_metrics.csv
│   ├── detection_results.csv
│   └── expected_power.csv
│
└── models/
    ├── linear_regression.joblib
    ├── random_forest.joblib
    ├── xgboost.joblib
    ├── lstm_model.keras
    ├── lstm_X_scaler.joblib
    ├── lstm_y_scaler.joblib
    └── isolation_forest_models.joblib
```

## Installation

Python 3.11 is a recommended starting point.

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/solar-monitoring-dashboard.git
cd solar-monitoring-dashboard
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Run the Dashboard

```bash
streamlit run app.py
```

The dashboard will normally open at:

http://localhost:8501

## Deployment

The application can be deployed through Streamlit Community
Cloud by connecting the GitHub repository and selecting `app.py`
as the application entry point.

## Important Limitations

- The dashboard uses historical observations, not live plant telemetry.
- Forecast charts display previously evaluated model predictions.
- The dashboard does not retrain models during operation.
- Anomaly alerts require engineering inspection before any
  physical fault can be confirmed.
- Power values retain the units reported in the source dataset.

## Technologies

- Python
- Pandas and NumPy
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- Plotly
- Streamlit
- Google Colab
- GitHub

## Author

Electrical Engineering | Artificial Intelligence |
Robotics | Renewable Energy

Developed as an applied AI and electrical engineering
portfolio project.
