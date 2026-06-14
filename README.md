# Telco Customer Churn Prediction Platform

**XGBoost • MLflow • FastAPI • Gradio • Docker • GitHub Actions • CI/CD**

A production-oriented machine learning platform that predicts telecom customer churn using an XGBoost classification model. The project demonstrates the complete machine learning lifecycle, including feature engineering, experiment tracking, model serving, containerization, and automated CI/CD deployment workflows.

Unlike traditional notebook-based ML projects, this platform exposes predictions through REST APIs and an interactive web application, enabling real-time inference and deployment-ready operation.

---

# 🎯 Business Value

Customer churn is one of the most critical challenges faced by telecom organizations. Identifying customers likely to leave enables businesses to take proactive retention actions before revenue loss occurs.

### Key Benefits

* Predict customer churn risk in real time.
* Support data-driven customer retention strategies.
* Reduce customer acquisition costs.
* Provide explainable insights into churn-driving factors.
* Enable scalable deployment through containerized infrastructure.

---

# 🏗 System Architecture

```text
                    User Requests
                           │
                           ▼
               ┌─────────────────────┐
               │     FastAPI API     │
               │                     │
               │  GET  /             │
               │  POST /predict      │
               └──────────┬──────────┘
                          │
         ┌────────────────┴───────────────┐
         ▼                                ▼
 ┌─────────────────┐           ┌──────────────────┐
 │   Gradio UI     │           │ Prediction Engine │
 │      /ui        │◄────────► │ XGBoost Model     │
 └─────────────────┘           └─────────┬────────┘
                                         │
                                         ▼
                           ┌────────────────────────┐
                           │ MLflow Model Artifacts │
                           │ Preprocessing Pipeline │
                           └────────────────────────┘
                                         │
                                         ▼
                                Docker Container
                                         │
                                         ▼
                             GitHub Actions CI/CD
                                         │
                                         ▼
                                    Docker Hub
```

---

# ⚙️ Technology Stack

## Machine Learning

* XGBoost
* Scikit-Learn
* Pandas
* NumPy

## Experiment Tracking

* MLflow
* Model Versioning
* Artifact Management

## Backend

* FastAPI
* Uvicorn

## Frontend

* Gradio

## MLOps & Deployment

* Docker
* GitHub Actions
* Docker Hub
* CI/CD Automation

---

# 📊 Model Performance

### XGBoost Classifier

| Metric    | Score  |
| --------- | ------ |
| Precision | 49.04% |
| Recall    | 82.09% |
| F1-Score  | 61.40% |
| ROC-AUC   | 83.67% |

### Performance Analysis

* High Recall minimizes missed churn-risk customers.
* Strong ROC-AUC demonstrates effective customer separation.
* Optimized for business scenarios where identifying potential churners is more important than maximizing precision.

---

# 📁 Project Structure

```text
Telco-Customer-Churn-ML
│
├── notebooks/
│   └── Exploratory analysis and experimentation
│
├── scripts/
│   └── Data processing and training automation
│
├── src/
│   ├── app/
│   │   ├── main.py
│   │   └── FastAPI application
│   │
│   ├── serving/
│   │   ├── prediction pipeline
│   │   ├── preprocessing logic
│   │   └── model artifacts
│   │
│   └── training/
│       └── model training workflow
│
├── mlruns/
│   └── MLflow experiments
│
├── Dockerfile
├── requirements.txt
├── README.md
└── .github/
    └── workflows/
        └── ci.yml
```

---

# 🚀 Core Features

## Automated Experiment Tracking

MLflow records:

* Hyperparameters
* Metrics
* Model artifacts
* Experiment history

This ensures complete reproducibility of model training.

---

## Production API Layer

FastAPI exposes the trained model through REST endpoints.

### Health Endpoint

```http
GET /
```

### Prediction Endpoint

```http
POST /predict
```

Enables integration with:

* Web applications
* Dashboards
* Mobile applications
* Enterprise systems

---

## Interactive Gradio Interface

A Gradio application is mounted directly inside FastAPI.

Accessible through:

```text
http://localhost:8000/ui
```

Allows:

* Manual testing
* Rapid validation
* Demonstrations
* Stakeholder feedback

---

# 🐳 Docker Containerization

The application is fully containerized using Docker.

### Benefits

* Environment consistency
* Simplified deployment
* Dependency isolation
* Improved reproducibility

### Build Image

```bash
docker build -t telco-churn-app .
```

### Run Container

```bash
docker run -p 8000:8000 telco-churn-app
```

---

# 🔄 CI/CD Pipeline

GitHub Actions automates deployment workflows.

### Pipeline Flow

```text
Code Push
    │
    ▼
GitHub Actions
    │
    ▼
Docker Build
    │
    ▼
Docker Hub Authentication
    │
    ▼
Docker Image Push
    │
    ▼
Deployment Ready Artifact
```

### Automated Steps

* Source code checkout
* Docker image build
* Dependency validation
* Docker Hub authentication
* Image publishing

---

# 🛠 Engineering Challenges & Solutions

## Dependency Version Conflicts

### Challenge

Package incompatibilities caused container build failures.

### Solution

Resolved version conflicts involving:

* Gradio
* Pillow
* MarkupSafe

and standardized dependency versions.

---

## Docker Runtime Errors

### Challenge

Container startup failures due to missing modules and import path issues.

### Solution

Refactored Docker configuration and standardized application startup procedures.

---

## MLflow Artifact Resolution

### Challenge

Model artifacts were not consistently located across environments.

### Solution

Implemented robust artifact-loading logic and standardized MLflow experiment management.

---

## CI/CD Authentication Issues

### Challenge

GitHub Actions failed during Docker Hub authentication.

### Solution

Configured secure authentication using:

* Docker Personal Access Tokens
* GitHub Secrets
* Automated workflow validation

---

# 📚 Local Quick Start

## Clone Repository

```bash
git clone <repository-url>
cd Telco-Customer-Churn-ML
```

## Build Container

```bash
docker build -t telco-churn-app .
```

## Run Container

```bash
docker run -p 8000:8000 telco-churn-app
```

---

# 🌐 Access the Application

### API Documentation

```text
http://localhost:8000/docs
```

### Interactive Interface

```text
http://localhost:8000/ui
```

---

# 🔮 Future Enhancements

* Cloud deployment (AWS/Azure/GCP)
* Model monitoring and drift detection
* Batch inference workflows
* Automated retraining pipelines
* Explainable AI integration
* User authentication and access control

---

# 👩‍💻 Author

**Samiksha Hujare**

B.Tech Computer Science & Engineering (Data Science)

Machine Learning • MLOps • Data Science • AI Systems
