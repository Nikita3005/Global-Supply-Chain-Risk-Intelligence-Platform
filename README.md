# 🚀 AI-Powered Supply Chain Risk Intelligence Platform

![Databricks](https://img.shields.io/badge/Platform-Databricks-orange)
![Python](https://img.shields.io/badge/Python-3.10-blue)
![MLflow](https://img.shields.io/badge/MLflow-Experiment%20Tracking-blue)
![Delta Lake](https://img.shields.io/badge/Data%20Lake-Delta%20Lake-green)
![Machine Learning](https://img.shields.io/badge/AI-Machine%20Learning-purple)
![Status](https://img.shields.io/badge/Project-Complete-success)

## 📌 Overview

Global supply chains involve complex logistics operations where delays, vendor reliability issues, and inefficient shipment modes can significantly impact delivery timelines and operational costs.

This project builds an **end-to-end data and AI platform using the Databricks Lakehouse architecture** to analyze shipment data, identify logistics risks, and predict shipment delays. The system integrates **data engineering, feature engineering, machine learning, experiment tracking, and interactive analytics dashboards** to provide actionable insights for supply chain decision-making.

The platform enables logistics teams to:

* Detect **high-risk vendors**
* Identify **shipment modes with higher delay probability**
* Analyze **cost vs delivery delay relationships**
* Predict shipment delays using machine learning
* Monitor logistics performance through **interactive dashboards**

---

## 🌟 Project Highlights

✔ End-to-end Databricks Lakehouse architecture  
✔ Medallion data architecture (Bronze → Silver → Gold)  
✔ Feature engineering for logistics risk intelligence  
✔ Machine learning delay prediction model  
✔ MLflow experiment tracking  
✔ Interactive SQL analytics dashboard  
✔ Supply chain operational insights



# 🏗 Solution Architecture

The system follows the **Medallion Architecture** pattern implemented within the Databricks Lakehouse.

```
                   ┌───────────────────────┐
                   │   Raw Shipment Data   │
                   └──────────┬────────────┘
                              │
                              ▼
                   ┌───────────────────────┐
                   │  Bronze Layer         │
                   │  Raw Data Ingestion   │
                   └──────────┬────────────┘
                              │
                              ▼
                   ┌───────────────────────┐
                   │  Silver Layer         │
                   │  Data Cleaning        │
                   │  Standardization      │
                   └──────────┬────────────┘
                              │
                              ▼
                   ┌───────────────────────┐
                   │  Gold Layer           │
                   │  Feature Engineering  │
                   │  Risk Metrics         │
                   └──────────┬────────────┘
                              │
                              ▼
                   ┌───────────────────────┐
                   │  ML Model             │
                   │  Logistic Regression  │
                   └──────────┬────────────┘
                              │
                              ▼
                   ┌───────────────────────┐
                   │  MLflow Tracking      │
                   │  Experiment Logging   │
                   └──────────┬────────────┘
                              │
                              ▼
                   ┌───────────────────────┐
                   │  SQL Dashboard        │
                   │  Risk Intelligence    │
                   └───────────────────────┘
```

---

# 🧱 Medallion Data Architecture

## 🥉 Bronze Layer – Raw Data Ingestion

The Bronze layer stores **raw shipment data** ingested directly into Delta tables without modification.

Key objectives:

* Preserve raw data for traceability
* Maintain ingestion timestamps
* Enable scalable data storage

Notebook:

```
01_bronze_ingestion
```

---

## 🥈 Silver Layer – Data Cleaning & Standardization

The Silver layer focuses on **data quality and transformation**.

Key transformations include:

* Date format standardization
* Handling malformed values
* Data type conversion
* Calculation of delivery delay days
* Creation of delay indicator (`is_delayed`)

Notebook:

```
02_silver_data_cleaning
```

---

## 🥇 Gold Layer – Feature Engineering

The Gold layer produces **analytics-ready and ML-ready features**.

Features engineered include:

| Feature                     | Description                       |
| --------------------------- | --------------------------------- |
| delivery_delay_days         | Delivery delay duration           |
| is_delayed                  | Binary delay indicator            |
| cost_per_kg                 | Freight cost efficiency           |
| vendor_delay_rate           | Vendor-level delay performance    |
| shipment_mode_delay_rate    | Delay risk by shipment type       |
| vendor_reliability_category | Vendor reliability classification |
| shipment_size_category      | Shipment size segmentation        |

Notebook:

```
03_gold_feature_engineering
```

---

# 📊 Logistics Risk Analytics

Using the Gold dataset, analytics queries were developed to identify operational risks in the supply chain.

Key analytics include:

* Shipment delay distribution
* Vendor risk analysis
* Shipment mode delay comparison
* Cost vs delivery delay analysis

Notebook:

```
04_logistics_risk_analytics
```

---

# 🤖 Machine Learning Model

A **Logistic Regression model** was trained to predict shipment delays.

### Target Variable

```
is_delayed
```

### Model Features

* vendor_delay_rate
* shipment_mode_delay_rate
* cost_per_kg
* shipment_size_category

### Model Outputs

* Delay prediction
* Delay probability

Notebook:

```
05_delay_prediction_model
```

---

# 📈 Experiment Tracking with MLflow

MLflow was used to track machine learning experiments including:

* Model parameters
* Evaluation metrics
* Model artifacts

Metrics logged include:

* Accuracy
* ROC-AUC score

This enables **reproducibility and experiment comparison**.

---

# 📊 Interactive SQL Dashboard

A Databricks SQL dashboard was created to visualize supply chain risk insights.

Key dashboard components:

### KPI Metrics

* Total Shipments
* Delayed Shipments
* Delay Rate (%)
* Average Delivery Delay

### Risk Analysis Visualizations

* Delay Rate by Shipment Mode
* Vendors with Highest Shipment Delay Rate
* Freight Cost vs Delivery Delay
* Vendor Reliability Distribution

These visualizations enable stakeholders to quickly identify operational risks and performance trends.


---
# 🤖 AI Insights using Databricks Genie

Natural language analytics powered by Databricks Genie.

Users can ask questions such as:

💬 Which vendors have the highest delay rate?

💬 Which shipment mode causes the most delays?

💬 Show cost vs delay trends.

Genie automatically generates SQL queries and visualizations for business users.

---
# 🔍 Key Insights

Analysis of the dataset revealed several important logistics insights:

• Ocean shipments show the highest delay rates among transportation modes

• Certain vendors consistently exceed average delay benchmarks

• Large shipment sizes correlate with higher delivery delays

• Higher freight cost per kg is associated with increased delay risk

These insights can support **vendor selection, route planning, and logistics optimization**.

---

# ⚙ Technology Stack

| Category            | Tools                 |
| ------------------- | --------------------- |
| Data Platform       | Databricks Lakehouse  |
| Storage             | Delta Lake            |
| Data Processing     | PySpark               |
| Machine Learning    | Scikit-learn          |
| Experiment Tracking | MLflow                |
| Analytics           | Databricks SQL        |
| Visualization       | Databricks Dashboards |

---

# 📂 Project Structure

```
Logistics-Risk-Analytics
│
├── Notebooks
│   ├── 01_bronze_ingestion
│   ├── 02_silver_data_cleaning
│   ├── 03_gold_feature_engineering
│   ├── 04_logistics_risk_analytics
│   └── 05_delay_prediction_model
│
├── Artifacts
│   ├── architecture_diagram.png
│   ├── pipeline_notebooks.png
│   ├── mlflow_experiment.png
│   ├── analytics_dashboard.png
│   └── genie_insights.png
│
└── README.md
```


# 💼 Business Impact

The Supply Chain Risk Intelligence Platform enables logistics and operations teams to move from reactive decision-making to proactive risk management.

Key benefits include:

• **Early identification of high-risk shipments** using predictive modeling  
• **Vendor performance monitoring** through delay rate analysis  
• **Transportation optimization** by identifying shipment modes with higher delays  
• **Cost efficiency insights** by analyzing freight cost versus delivery performance  

By integrating machine learning with analytics dashboards, the platform allows supply chain managers to quickly detect operational inefficiencies and take corrective actions before delays escalate.

This approach supports data-driven supply chain optimization, improves delivery reliability, and reduces operational risk.


---

# 🚀 Future Improvements

Potential future enhancements include:

* Advanced ML models (Random Forest, Gradient Boosting)
* Real-time data ingestion pipelines
* Automated model retraining workflows
* Supply chain anomaly detection
* Integration with external logistics systems

---

# 📌 Conclusion

This project demonstrates how the **Databricks Lakehouse platform can be used to build an end-to-end supply chain risk intelligence system**, combining data engineering, machine learning, and analytics.

The solution provides actionable insights that can help logistics teams improve operational efficiency, reduce shipment delays, and make data-driven supply chain decisions.

---
