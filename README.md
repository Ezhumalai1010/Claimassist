# Claimassist
# Claims Anomaly Detection & Monitoring System

An AI-powered claims/authorization anomaly detection system designed to identify suspicious authorization patterns using machine learning and provide real-time anomaly scoring through a web application.

The project combines feature engineering, an Autoencoder-based representation model, and Logistic Regression for supervised anomaly classification.

---

## 🚀 Project Overview

Healthcare authorization and claims data can contain unusual patterns such as:

- Excessive requested units
- Duplicate authorization bursts
- Ghost providers
- Unauthorized specialties
- Impossible decision dates
- Mass auto-approvals
- After-death authorizations

The objective of this project is to automatically identify potentially anomalous authorization records and provide an easy-to-use monitoring interface for users.

---

## 🧠 Machine Learning Approach

The final model uses an:

**Autoencoder + Logistic Regression**

pipeline.

### Architecture

```text
Original Features
       │
       ▼
Feature Engineering
       │
       ▼
25 Input Features
       │
       ▼
Autoencoder
25 → 12 → 8 → 12 → 25
       │
       ▼
Latent Representation
       │
       ├───────────────┐
       │               │
       ▼               ▼
8 Latent Features   Reconstruction Error
       │               │
       └───────┬───────┘
               ▼
      Logistic Regression
               │
               ▼
       Anomaly Probability
               │
               ▼
       Decision Threshold
          Threshold = 0.81
               │
               ▼
      Normal / Anomalous
