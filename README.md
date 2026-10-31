![Python](https://img.shields.io/badge/Python-3.9+-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?logo=fastapi)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?logo=scikit-learn)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker)
![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)


## 🚨 Network Intrusion Detection API (ML + FastAPI + Docker)

A production-ready machine learning system for detecting malicious network traffic in real time, deployed as a scalable REST API.

### 🔍 Overview

Cyberattacks are becoming more frequent and complex, making traditional rule-based intrusion detection systems ineffective. This project implements a machine learning–driven Intrusion Detection System (IDS) that classifies network traffic as Normal or Attack based on flow-level features.

The solution goes beyond model training by delivering a fully deployed ML system, exposed via FastAPI and packaged with Docker for real-world usability.

###  Why This Project Matters

This project demonstrates end-to-end ML engineering, not just algorithms.
```
✔ Real-world dataset
✔ Highly imbalanced classification problem
✔ Robust preprocessing with pipelines
✔ Probabilistic decision-making with thresholds
✔ API-first deployment mindset
✔ Containerized for portability
```
###  Machine Learning Design
### Problem Type

#### Binary Classification

0 → Normal / Benign Traffic
1 → Intrusion / Attack

#### Model

- Random Forest Classifier
- Strong baseline for tabular data
- Handles non-linear relationships
- Robust to noise and imbalance
- Minimal feature scaling requirements

### Key Techniques

- ColumnTransformer-based preprocessing
- One-hot encoding for categorical features
- Median & mode imputation
- Class imbalance handling
- Probability-based decision thresholding

### 📊 Model Performance

The model achieves near-perfect separation between normal and attack traffic.

### Confusion Matrix

![Confusion Matrix](images/confusion_matrix.png)

### ROC Curve

![ROC Curve](images/roc-curve.png)

### Precision–Recall Curve

![PR Curve](images/precision-curve.png)

### Feature Importance

![Feature Importance](images/feature-importance.png)

### 🏗️ System Architecture
```
Raw Network Flow Data
        ↓
Feature Engineering
        ↓
ML Pipeline (Preprocessing + Model)
        ↓
FastAPI Prediction Service
        ↓
Docker Container
```

### 🚀 API Design

GET /health

### Response
```
{
  "status": "ok",
  "version": "1.0.0",
  "model_loaded": true
}
```
### 🔹 Predict Intrusion

POST /predict

### Response
```
{
  "predicted_category": 1,
  "traffic_type": "Attack",
  "confidence": 0.91,
  "decision_threshold": 0.80
}
```
✔ Human-readable output
✔ Probability transparency
✔ Adjustable decision threshold

### 🐳 Dockerized Deployment
#### Build Image
```
docker build -t intrusion-detection-api .
```
#### Docker Hub Image
You can pull and run the container directly from Docker Hub:
```
docker pull dataforai/intrusion-detection-api
```
#### Run Container
```
docker run -p 8000:8000 intrusion-detection-api
```
#### 📍 API available at:
```
http://localhost:8000
```
### 📂 Project Structure

```
.
├── app.py
├── model/
│   └── rfmodel.pkl
├── schema/
│   ├── user_input_pydantic.py
│   └── prediction_response.py
├── images/
│   ├── confusion_matrix_rf.png
│   ├── roc_curve.png
│   ├── pr_curve.png
│   └── feature_importance.png
├── requirements.txt
├── Dockerfile
|__dockerignore
└── README.md
```
### 🧪 Tech Stack

- Python
- Scikit-learn
- Pandas / NumPy
- FastAPI
- Pydantic
- Docker
- Joblib

### 👩‍💻 Author

Divya Raut
Junior Machine Learning Engineer | Data Scientist

🔗 GitHub: https://github.com/dataraftai
