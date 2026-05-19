# Cem Özçelik

**Target Roles:** Senior Data Scientist | ML Engineer | Senior Data Analyst
**Location:** Istanbul, Turkey (open to remote / hybrid / EU relocation)
**Phone:** +90 553 473 4556
**Email:** i.cemozcelik@gmail.com
**LinkedIn:** linkedin.com/in/cemozcelık
**GitHub:** github.com/ccemozclk

## Summary

Senior Data Scientist with an Industrial Engineering background and 4+ years of progressive experience spanning data analytics, predictive modeling, and end-to-end ML system deployment. Specialized in anomaly detection, financial risk modeling, and predictive maintenance — with proven impact across manufacturing, supply chain, and financial domains.

Strong combination of deep technical expertise (TensorFlow, PyTorch, XGBoost, PySpark) and engineering rigor (MLOps, Docker, FastAPI/Django deployment). Bridges advanced AI theory with operations research principles to deliver measurable business outcomes — including a 15% increase in critical machine availability via predictive maintenance, 97% recall on medical diagnostic models, and an 8-hour weekly reduction in operational overtime through ML-driven supply chain forecasting.

Comfortable owning the full lifecycle: from raw data ingestion and feature engineering, through model training and validation, to containerized deployment and RESTful API integration.

## Experience

### Anadolu Pet Akvaryum & Effeffe — Senior Database Analyst
*Jan 2026 – Present | Maltepe, Istanbul*

- Spearheaded the architectural scaling of a custom Django web application, transitioning it from an internal reporting tool into a centralized hub for deploying ML models via RESTful APIs.
- Directed advanced predictive operations using Python-based supply chain algorithms, sustaining an **8-hour weekly reduction in operational overtime** and architecting robust pipelines for AI-driven forecasting.
- Led cross-functional data initiatives, translating SKU-level Association Rule Mining outputs into strategic business actions that drove continuous revenue growth.
- **Tech:** Python, Django, REST APIs, ML pipelines, Association Rule Mining, PostgreSQL, Docker

### Anadolu Pet Akvaryum & Effeffe — IT & Data Analytics Specialist
*Sept 2024 – Dec 2025 | Maltepe, Istanbul*

- Architected, developed, and deployed a full-stack internal web application from scratch using Python (Django) and SOLID principles — establishing foundational software engineering and deployment practices.
- Engineered initial predictive supply chain optimization models using Python and PL/SQL, **reducing stockouts and improving inventory turnover**.
- Conducted Route-Level Profitability Analysis with advanced SQL, defining cost-to-profit ratios that delivered a **3% improvement in overall logistics efficiency**.
- **Tech:** Python, Django, PL/SQL, Oracle, SOLID, full-stack deployment

### Birinci Automotive — Mid-Level Data Analyst
*Jan 2022 – Sept 2024 | Çayırova, Kocaeli*

- Engineered robust ETL pipelines in MSSQL and Python to ingest and process high-volume manufacturing and machine sensor data, replacing manual reporting workflows.
- Developed a **Predictive Maintenance & Anomaly Detection framework** using unsupervised clustering on historical machine failure patterns, delivering a **15% weekly increase in critical machine availability**.
- Processed and analyzed complex time-series data from machine sensors for cycle time optimization, building a strong foundation for sequential modeling (RNNs).
- Bridged raw production data and operational strategy, **improving Overall Equipment Effectiveness (OEE) by 15%**.
- **Tech:** Python, MSSQL, ETL, unsupervised clustering, time-series analysis

### Birinci Automotive — Junior Data Analyst
*June 2021 – Jan 2022 | Çayırova, Kocaeli*

- Conducted Exploratory Data Analysis (EDA) and applied statistical methods to workforce datasets, uncovering hidden patterns to optimize HR policies.
- Designed and implemented automated data workflows and ingestion pipelines, **improving reporting efficiency by 15%**.
- Collaborated with engineering teams to align workforce productivity metrics with manufacturing OEE goals.
- **Tech:** Python, SQL, statistical analysis, ETL

## Skills

**Languages & Core:** Python (Advanced), SQL (Advanced), Bash, JavaScript (Basics)

**Machine & Deep Learning:** TensorFlow, Keras, PyTorch, Scikit-learn, XGBoost, h2o.ai, CNNs, RNNs, Computer Vision, Explainable AI (Grad-CAM), Transfer Learning, Fine-Tuning

**MLOps, Web & Deployment:** Docker, Flask, FastAPI, Django, RESTful APIs, Git, Linux, End-to-End ML Deployment

**Big Data & Cloud:** Apache Spark (PySpark), Databricks, AWS (EC2, S3), Distributed Computing

**Data Engineering & Databases:** PostgreSQL, MSSQL, Oracle, ETL Pipelines, Pandas, NumPy

**Advanced Concepts:** OOP, API & System Architecture, A/B Testing & Experiment Design, Cost-Function Optimization, Mixed-Integer Programming (MILP), Multi-Criteria Decision Making (AHP, TOPSIS)

## Education

### Kırıkkale University — B.Sc. Industrial Engineering
*Sept 2016 – Feb 2021 | Kırıkkale, Turkey*

- Built a rigorous mathematical foundation in statistical analysis, linear algebra, and calculus — direct prerequisites for Deep Learning architectures.
- Designed complex optimization models with IBM ILOG CPLEX (MILP), connecting traditional operations research with modern cost-function optimization (Gradient Descent).
- Applied Multi-Criteria Decision Making (AHP, TOPSIS) to multi-objective optimization problems, building intuition for AI system design tradeoffs.

### Datacamp — Associate Data Scientist Career Track
*Jan 2024 – May 2024*

- Specialized modules: PySpark, Feature Engineering, Recommendation Engines (ALS).
- Transitioned from local analysis to distributed computing.

### Miuul — Data Science & Machine Learning Bootcamp
*Mar 2022 – Sept 2022*

- 6-month intensive, hands-on bootcamp covering the end-to-end ML lifecycle.
- Delivered 10+ real-world projects in classification, regression, and clustering.

## Languages

- **Turkish:** Native
- **English:** Fluent
- **Spanish:** Basic

## Selected Projects

### End-to-End Credit Risk Prediction — MLOps & Financial Risk
- **63% F1-Score** with XGBoost on Lending Club dataset, optimized for heavy class imbalance with temporal holdout validation (no leakage)
- Full MLOps pipeline: raw data ingestion → feature engineering → model training → containerized production app
- Interactive EDA platform built with Django so non-technical reviewers can explore data and model decisions
- Architecture pattern transfers directly to **fraud detection, payment intelligence, and behavioral anomaly modelling**
- **Tech:** Python, XGBoost, CatBoost, Django, Docker, Pandas, Scikit-learn
- **Repo:** github.com/ccemozclk/Credit-Risk

### AI-Powered Medical Diagnostics — Explainable AI & Cost-Function Optimization
- **97% Recall** on pneumonia detection from chest X-rays — explicitly optimized for asymmetric error cost (False Negative >> False Positive in clinical context)
- **93% Test Accuracy** with Fine-Tuned VGG16 (vs. 76% baseline CNN, 81% ResNet50) — comparative architecture study
- Implemented **Grad-CAM** for visual explainability; identified and corrected a dataset bias invisible without heatmap analysis
- Class weight balancing + surgical fine-tuning of `block5` with low learning rate (1e-5) for medical pattern adaptation
- **Tech:** Python, TensorFlow-Keras, VGG16, ResNet50, OpenCV, Grad-CAM
- **Repo:** github.com/ccemozclk/Deep-Learning-Project-CNN-VGG16-ResNet50

### Retail Demand Forecasting — End-to-End MLOps Pipeline
- **~12.83% RMSPE** on 6-week daily sales forecasting across 1,115 Rossmann stores using time-based validation (no temporal leakage)
- Object-oriented training pipeline (DataIngestion → DataTransformation → ModelTrainer) replacing static notebook code
- FastAPI REST inference + Streamlit dashboard with **dynamic confidence intervals** translating ML metrics to business terms (€ margin of error)
- Resilient inference layer handling unseen categorical inputs in production
- Surfaced actionable business insight: B-type stores yield lower promotion ROI vs A/C — enabled marketing budget reallocation
- **Tech:** Python, LightGBM, XGBoost, Optuna, FastAPI, Streamlit, Docker
- **Repo:** github.com/ccemozclk/Rossman-Demand-Forecasting

### E-Commerce AI Search Engine — Semantic Search & Recommendation
- **Production-ready microservices architecture** with dual-engine A/B testing: SentenceTransformers (`all-MiniLM-L6-v2`) vs custom-trained Word2Vec on 800K+ product descriptions
- Custom **LSTM next-token prediction** model in PyTorch for intelligent search auto-complete
- **Item2Vec collaborative filtering** for "Frequently Bought Together" recommendations on hundreds of thousands of user sessions
- Sub-millisecond cached responses via Redis; PySpark distributed ETL for massive JSONL ingestion
- **Tech:** PyTorch, FastAPI, Streamlit, Qdrant (Vector DB), Redis, PySpark, Docker, SentenceTransformers
- **Repo:** github.com/ccemozclk/amazon-ai-search-engine

### Bidirectional LSTM Sentiment Analysis — NLP & Sequential Data
- **88.54% Validation Accuracy** with custom 2-layer Bi-LSTM trained from scratch (no pre-trained embeddings) on 50K IMDB reviews
- Designed unified preprocessing pipeline supporting both Kaggle CSV and Hugging Face dataset formats
- Solved exploding gradient with norm clipping (clip=5); 50% dropout for generalization
- Successfully handles linguistic edge cases: irony, double negatives, contextual shifts (validated with manual inference tests)
- **Tech:** PyTorch, Hugging Face Datasets, Custom nn.Module Architecture
- **Repo:** github.com/ccemozclk/Sentiment-LSTM-PyTorch

### Scalable Recommendation Engine — PySpark & Customer Segmentation
- End-to-end personalized recommendation system on Apache Spark/Databricks for retail (Online Retail II)
- **RFM analysis + K-Means** for behavioral customer segmentation into 5 strategic segments (Champions, At-Risk, etc.)
- **ALS collaborative filtering** with implicit feedback (purchase quantity as proxy) and cold-start handling
- Generated logically validated personalized recommendations (e.g., themed product affinities mapped correctly)
- **Tech:** PySpark, Apache Spark, Databricks, Streamlit, K-Means, ALS
- **Repo:** github.com/ccemozclk/Spark-Recommendation-Engine
