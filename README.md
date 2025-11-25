⚡ Deep Learning for Household Energy Forecasting
LSTM | GRU | CNN-LSTM | Transformer | Weighted Ensemble | Streamlit App | Production-Ready API
# deep-learning-energy-forecasting
End-to-end Deep Learning Capstone Project | Energy Forecasting using LSTM, GRU, CNN-LSTM, Transformer, and Weighted Ensemble | Streamlit App + Deployment
📌 Project Overview

This repository contains an end-to-end Deep Learning system for forecasting household electrical energy consumption using the Individual Household Electric Power Consumption dataset (2006–2010, ~2M rows).

The solution includes:

Complete data engineering pipeline

Multimodel deep learning experimentation

Model comparison and hyperparameter optimization

GRU + Transformer weighted ensemble

Production-ready deployment (Streamlit + API)

Research-grade documentation and visuals

This project can be used as a portfolio showcase, interview demonstration, or real-world forecasting engine.
📚 Research Report

The full write-up—including theory, methodology, model comparison, ensemble strategy, and business value—is available here:
📄 Deep Learning Ensembles for Time-Series Energy Forecasting
🧠 Key Features
1. Advanced Data Engineering

Parsing 2M+ minute-level records

Hour-level resampling

Dual-layer missing value imputation (time-interpolation + seasonal hourly mean)

Feature engineering:

Lag features (Lag-1, Lag-24, Lag-48)

24-hour rolling statistics

Calendar features (hour, day, month, weekend)

MinMax scaling with leakage-free splitting

2. Multimodel Deep Learning

Trained and evaluated:

Architecture	Summary
LSTM Baseline	Benchmark RNN
Stacked LSTM	Multiple LSTM layers (dropout-regularized)
GRU	High accuracy + efficient
CNN-LSTM	Combines convolution + sequence modeling
Transformer	Multi-Head Self-Attention for global temporal patterns
3. Weighted Ensemble (Production Model)

Based on the report’s experimental findings (pages 6–10)
GRU → lowest MAE

Transformer → best pattern capture

Final ensemble:

60% GRU + 40% Transformer = Balanced accuracy + generalization

4. Deployment

Streamlit UI for interactive forecasting

Prediction service powered by predict.py

Model + scaler exported (.keras, .pkl)

Ready for cloud deployment (Railway, Render, AWS EC2, Docker)
📊 Model Performance
| Model                            | Test MSE   | Test MAE   | Outcome                  |
| -------------------------------- | ---------- | ---------- | ------------------------ |
| **GRU**                          | 0.0187     | 0.1100     | Best individual model    |
| **Transformer**                  | 0.0234     | 0.1183     | Best pattern recognition |
| LSTM Baseline                    | 0.0220     | 0.1212     | Good benchmark           |
| LSTM Improved                    | 0.0493     | 0.1833     | Overfitting              |
| CNN-LSTM                         | 0.0756     | 0.2193     | Poor generalization      |
| **GRU + Transformer (Ensemble)** | **0.0196** | **0.1116** | Production model         |
🚀 Run the Streamlit App (Local Deployment)
1. Install dependencies
pip install -r requirements.txt

2. Start Streamlit
streamlit run src/dashboard.py

3. Upload 24-hour input window

The UI will display:

Processed window

Predicted next-hour energy

True vs predicted comparison (if actuals available)
⚡ FastAPI Backend (Prediction API)

Start API:

uvicorn src.app:app --reload
📦 Exported Production Assets

final_best_model.keras → Ensemble prediction model

scaler.pkl → MinMaxScaler

predict.py → Unified inference pipeline

utils.py → Sequence builder

🧪 Reproducibility

All experiments (plots, model training, hyperparameters, metrics) are stored inside:

notebooks/Deep_Learning.ipynb

Report document (pages 1–12)

👤 Author

Niraj Karande
Data Analyst | Machine Learning Practitioner
