🔍 Building Energy Anomaly Detection
📌 Project Overview

This project focuses on detecting anomalies in building energy consumption using machine learning techniques. The dataset is derived from the Building Data Genome 2 (BDG2), containing multiple energy meter readings including electricity, gas, water, solar, and more.

The goal is to identify unusual energy consumption patterns, estimate their financial impact, and provide actionable insights for energy optimization.

📊 Key Features

Aggregated multi-source energy data (electricity, gas, water, etc.)

Time-series feature engineering

Anomaly detection using:

Isolation Forest

Visualization of anomalies in energy consumption

Business insights including:

Cost estimation

Seasonal patterns

Peak anomaly hours

Anomaly classification (Spike, Drop)

🗂 Dataset

Source: Building Data Genome Project 2 (BDG2)

Format: CSV files from multiple energy meters

Aggregated to hourly time-series data

⚙️ Project Pipeline
1️⃣ Data Loading & Aggregation

Loaded multiple meter datasets

Aggregated values by timestamp

2️⃣ Data Cleaning & Preprocessing

Converted timestamps to datetime

Sorted chronologically

Handled missing values by filling NaN with 0

Removed duplicates

3️⃣ Feature Engineering

Rolling mean (24-hour window)

Energy difference from previous timestamp

Time features (hour, day, month, day of week, weekend)

Total energy column (sum of all meters)

4️⃣ Feature Scaling

StandardScaler applied to numeric features

Normalizes features (mean ≈ 0, std ≈ 1) for model performance

5️⃣ Model Building

Isolation Forest

Parameters: n_estimators = 100, contamination = 0.01, random_state = 42

6️⃣ Anomaly Detection

Detected anomalies labeled in dataset

Output Files:

energy_anomaly_output.csv — full dataset with anomaly labels

only_anomalies.csv — anomalies only

7️⃣ Visualization

Total Energy Trend with anomalies

Hourly anomaly counts

Monthly anomaly distribution

📈 Results

Total anomalies detected: 176

Normal points: 17,368

Anomaly types:

Spike: 104

Drop: 21

Minor fluctuations: 107

Estimated cost impact: $6,267,192

Peak anomaly months: June, March, April

Peak hours: 7–9 AM, 2–3 PM

📊 Visualizations

Total energy over time with anomaly points

Monthly anomaly distribution

Hourly anomaly pattern

Feature importance approximation (based on variance/contribution)

🧠 Technologies Used

Python 3.x

Pandas, NumPy

Scikit-learn (Isolation Forest, StandardScaler)

Matplotlib, Seaborn

Jupyter Notebook