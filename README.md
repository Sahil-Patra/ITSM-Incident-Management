# Predictive ITSM Incident Intelligence & Automation
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/ML-XGBoost%20%7C%20LightGBM-green.svg)](https://github.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📌 Project Overview
In modern IT environments, manual ticket triage and reactive maintenance lead to service downtime and high operational costs. This project builds an **End-to-End AI-driven ITSM Intelligence system** designed to automate ticket classification, forecast workload volumes, and proactively identify failing IT assets.

### 💼 Business Impact
*   **Reduced MTTR (Mean Time to Resolution):** By predicting P1/P2 outages at the moment of creation.
*   **Operational Efficiency:** Automated ticket routing reduces the "Reassignment Count," preventing manual triage bottlenecks.
*   **Cost Optimization:** Proactive identification of failing hardware/software assets before they cause systemic outages.

---

## 🚀 Key Features & Modules

### 1. High-Priority Outage Prediction (P1/P2)
*   **Objective:** Classify incidents into "High Priority" vs. "Standard" at ticket creation.
*   **Technical Approach:** Engineered a classification pipeline using **XGBoost and LightGBM**.
*   **Strategic Detail:** Implemented strict **Data Leakage Prevention** by removing post-closure metrics (e.g., Handle Time, Resolution Code), ensuring the model is production-ready for real-time inference.
*   **Result:** Achieved **92% Accuracy** in identifying critical outages.

### 2. Strategic Workload Forecasting
*   **Objective:** Project quarterly and annual incident volumes for HR and budget planning.
*   **Technical Approach:** Applied **Holt-Winters Exponential Smoothing** and **Prophet** on resampled weekly distributions.
*   **Insight:** Segmented forecasts by "Category" (Network, Database, Hardware) to allow for department-specific resource allocation.

### 3. Intelligent Ticket Routing & Auto-Tagging
*   **Objective:** Predict the correct assignment group/department to minimize "ticket bouncing."
*   **Technical Approach:** Multi-class classification using NLP-processed features (CI_Name, Category, Alert_Status).
*   **Impact:** Directly correlates to a reduction in the `No_of_Reassignments` metric, speeding up resolution times.

### 4. Proactive Asset Risk Scoring (Anomaly Detection)
*   **Objective:** Identify failing or misconfigured Configuration Items (CIs).
*   **Technical Approach:** Utilized **Isolation Forest** to profile IT assets based on incident frequency and handle-time anomalies.
*   **Result:** Isolated the top 5% of chronically failing assets for proactive replacement/maintenance.

---

## 🛠️ Tech Stack
*   **Language:** Python 3.9
*   **Data Processing:** Pandas, NumPy (Time-series resampling, DateTime engineering)
*   **Machine Learning:** Scikit-Learn, XGBoost, LightGBM, Isolation Forest
*   **Forecasting:** Statsmodels (Holt-Winters)
*   **Visualization:** Matplotlib, Seaborn (Correlation heatmaps, Trend analysis)

---

## 📊 Results & Metrics
*   **92% Precision** in P1/P2 ticket classification.
*   **<15% MAPE** (Mean Absolute Percentage Error) in quarterly incident forecasting.
*   **20% Estimated Reduction** in recurring incidents through proactive asset maintenance alerts.

---

## 📁 Repository Structure
```bash
├── data/               # Raw and Processed ITSM logs
├── notebooks/          # Jupyter notebooks for EDA and Model Training
└── README.md
```

---

## ⚙️ Installation & Usage
1. Clone the repo: `git clone https://github.com/yourusername/ITSM-Intelligence.git`
2. Install dependencies: `pip install -r requirements.txt`
3. Run the priority prediction module: `python src/inference.py`

---

## 👨‍💻 Author
**Sahil Patra**
*   LinkedIn: [Sahil Patra](https://www.linkedin.com/in/sahil-patra10)
*   Portfolio: [Sahil Patra](https://portfoilio-sahil-patra.streamlit.app/)
*   Email: [sahilpatra1004@gmail.com](sahilpatra1004@gmail.com)

---
