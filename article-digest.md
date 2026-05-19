# Article Digest — Cem Özçelik

Personal proof points and behavioral interview stories in STAR+R format (Situation, Task, Action, Result, Reflection). These stories anchor the AI evaluation against my real track record and serve as raw material for tailored interview prep.

---

## Story 1: Predictive Maintenance Saves Critical Production Capacity

**Situation:** At Birinci Automotive (Tier-1 supplier in Kocaeli), unplanned breakdowns of critical CNC and stamping machines were the #1 driver of production line stoppages. Maintenance was reactive — by the time a sensor reading hit a hard threshold, downtime had already started. Manual reporting and Excel-driven workflows meant nobody could see failure patterns across hundreds of machines.

**Task:** Build a system that could detect anomalous machine behavior *before* breakdowns occurred, using only the historical sensor data we already collected.

**Action:**
- Engineered ETL pipelines in MSSQL and Python to ingest high-frequency time-series sensor data from the shop floor, replacing manual reporting workflows.
- Performed deep EDA on years of historical breakdown logs, mapped them against sensor signatures, and identified candidate features (vibration variance, cycle time drift, temperature deltas).
- Built an unsupervised clustering framework on historical failure patterns rather than relying on labeled anomalies (which were sparse and noisy).
- Validated against held-out failure events, tuned for precision over recall to avoid alarm fatigue on the floor.
- Trained shift supervisors on how to interpret alerts and integrate them into preventive maintenance scheduling.

**Result:**
- **15% weekly increase in critical machine availability.**
- **15% improvement in Overall Equipment Effectiveness (OEE).**
- Replaced manual Excel reporting with a sustainable data pipeline.
- Established the technical and cultural foundation for further ML adoption in the plant.

**Reflection:** The model was the easiest part. The hardest 70% was getting maintenance crews to *trust* alerts that came from "the computer" instead of from their decades of intuition. The lesson: ML in industrial settings lives or dies on operational adoption, not on F1 scores. I now always design with the human consumer of the prediction in mind from day one.

---

## Story 2: From Reporting Tool to ML Deployment Platform

**Situation:** When I joined Anadolu Pet Akvaryum & Effeffe, the company had a Django web app I built earlier as an internal reporting tool — mostly dashboards and SQL views. Leadership wanted to start deploying predictive models (demand forecasting, association rule mining for cross-sell), but there was no infrastructure to serve them. The default option on the table was to spin up new services for each model. I argued that was the wrong move.

**Task:** Re-architect the existing Django application so it could host and serve multiple ML models via REST APIs without becoming an unmaintainable monolith.

**Action:**
- Refactored the codebase along SOLID principles: separated model-serving logic into independent service modules with clean interfaces.
- Designed a versioned REST API layer (Django REST Framework) so that downstream consumers (operations team dashboards, supply chain automation scripts) could call models without coupling to internal implementation.
- Containerized the application with Docker for consistent deployment.
- Set up a model registry pattern so retraining and deployment didn't require touching API code.
- Migrated the supply chain forecasting models from standalone scripts into the new architecture as the first production load.

**Result:**
- One central platform serving all internal ML models — no more scattered scripts and ad-hoc deployments.
- **Sustained 8-hour weekly reduction in operational overtime** thanks to the predictive supply chain pipeline running on the new infrastructure.
- New models can now be deployed in days, not weeks, because the integration pattern is reusable.
- The platform became the canonical hub for "anything ML" inside the company.

**Reflection:** Engineers love new tools. But the most valuable architectural move I've made was *not* introducing a new stack — it was extending what already worked. Every team I've joined has had a "rewrite from scratch" temptation. Resisting it almost always pays off, *if* the existing system has good bones.

---

## Story 3: Medical Diagnostic AI — Optimizing for Cost of Error

**Situation:** I wanted to push my deep learning skills past tutorials and into a domain where the *cost of being wrong* was concrete and asymmetric. Pneumonia detection from chest X-rays was the perfect testbed: a False Negative (missed pneumonia) is potentially fatal; a False Positive (over-diagnosis) is recoverable. Default Kaggle approaches optimize for accuracy. That's the wrong loss function for clinical reality.

**Task:** Build an end-to-end diagnostic support system that explicitly prioritized **Recall** over accuracy, while remaining trustworthy enough that a clinician could rely on it.

**Action:**
- Used Transfer Learning with VGG16 and ResNet50 backbones (TensorFlow-Keras) to leverage ImageNet representations on a small medical dataset.
- Conducted surgical fine-tuning — selectively unfreezing top layers to adapt to medical features without overfitting.
- Engineered the training pipeline to handle class imbalance (oversampling, class weights), and tuned the decision threshold post-hoc to push Recall up at the cost of some precision.
- Implemented **Grad-CAM** to generate heatmap visualizations showing *where* in the X-ray the model was looking. This let me verify the model was attending to actual lung opacities and not artifacts (e.g., medical text annotations on the image — a known dataset bias).

**Result:**
- **97% Recall** — meaning the system would miss only 3 in 100 pneumonia cases.
- Established clinical trust through explainability: every prediction was paired with a visual heatmap.
- Identified and corrected a dataset bias I would have missed without Grad-CAM (the model was partially keying off image text, not pathology).
- Project published on GitHub as a reference implementation of XAI in medical imaging.

**Reflection:** This project changed how I frame every ML problem. The first question is no longer "what's the accuracy ceiling?" — it's "what does it cost when this model is wrong, in each direction?" That single reframing is the difference between a notebook demo and a system someone would actually deploy.

---

## Story 4: Credit Risk Model — From Notebook to Production

**Situation:** Most ML portfolios stop at "model trained, F1 reported." That's where production begins, not ends. I wanted to build a financial anomaly detection system that demonstrated I understood the *full* lifecycle — from raw, messy data to a deployable, containerized application — using the Lending Club credit dataset as a fraud-analogous problem.

**Task:** Architect a complete MLOps pipeline: data ingestion, feature engineering, model training under heavy class imbalance, and a production-ready interactive application.

**Action:**
- Treated severe class imbalance (defaults are <15% of the data) as a first-class design constraint, not an afterthought. Compared SMOTE, undersampling, and class-weighted loss; settled on a class-weighted XGBoost.
- Built reproducible feature engineering as a versioned pipeline — same transformations applied at training time and at inference time.
- Containerized everything with Docker so the application could run identically on my laptop, a server, or a cloud VM.
- Built an interactive EDA + prediction platform on top of Django so non-technical reviewers could explore the data and the model's decisions.

**Result:**
- **63% F1-Score** under heavy imbalance — solid for this dataset class, and validated on temporal holdout (no leakage).
- Full MLOps walkthrough documented end-to-end, demonstrating software engineering rigor alongside data science.
- The architecture pattern transfers directly to fraud detection / payment intelligence problems with minimal modification.

**Reflection:** The credit/fraud world is where data science most clearly intersects with business cost: every false positive is a frustrated customer, every false negative is real money lost. I designed this project specifically to be a bridge between my industrial engineering "cost-of-error" instinct and modern ML deployment practice — and it's the project I most often anchor financial-domain interviews around.

---

## Story 5: Recommendation Engine at Scale — Distributed Computing Discipline

**Situation:** Local Pandas-based analysis hits a wall when datasets cross the few-million-row mark. To work credibly in industries like e-commerce or telecom, distributed computing isn't a nice-to-have. I built a personalized recommendation system from scratch on Apache Spark to force myself out of the single-machine comfort zone.

**Task:** Build an end-to-end recommendation engine — segmentation + collaborative filtering — using PySpark and Databricks on a large-scale, unstructured behavioral dataset.

**Action:**
- Performed feature engineering and outlier filtering at distributed scale on Databricks.
- Implemented **K-Means clustering** for behavioral customer segmentation as a first layer (cold-start friendly).
- Layered **ALS (Alternating Least Squares) collaborative filtering** on top to drive personalized item-level recommendations.
- Tuned for the actual business KPI (conversion rate uplift), not just RMSE on the rating matrix.
- Wrestled honestly with Spark-specific issues: data skew, executor memory tuning, broadcast joins.

**Result:**
- A working end-to-end recommender on a real distributed stack.
- Demonstrable competence with PySpark, Databricks, and the operational realities of big-data ML.
- The project is the credibility anchor in any interview that touches "how do you handle scale."

**Reflection:** Going from a 50K-row laptop notebook to a multi-million-row distributed pipeline isn't a linear difficulty increase — it's a different game. Spark forces you to think about *where* computation happens, *how* data is partitioned, and *when* shuffles are cheap or expensive. Every data scientist eventually has to learn this. Better to learn it on a portfolio project than in a Monday production incident.

---

## Story 6: Industrial Engineering Roots — Why I Think About Cost Functions Differently

**Situation:** I'm not a CS-undergrad data scientist. I came from Industrial Engineering at Kırıkkale University, with deep coursework in operations research, optimization, and multi-criteria decision-making. Many people see this as a non-traditional path; I see it as the unfair advantage that makes my ML work different.

**Task:** Connect classical optimization theory (Linear Programming, MILP, AHP, TOPSIS) with modern machine learning practice — and use that bridge to design models that actually optimize for business outcomes, not just statistical metrics.

**Action:**
- Designed and solved real production and inventory optimization problems with **IBM ILOG CPLEX** using Linear Programming and Mixed-Integer Programming.
- Modeled real-world constraints — capacity, routing, multi-echelon inventory — that most ML practitioners never have to think about.
- Applied **AHP and TOPSIS** to multi-criteria decision problems where there's no single objective function to optimize, only weighted tradeoffs.
- Carried this discipline directly into my ML work: every model I build is framed as a cost-function optimization problem with explicit business cost weights, not as accuracy-chasing.

**Result:**
- A genuinely different approach to ML problems: I always start with "what's the cost matrix?" rather than "what's the model architecture?"
- This framing has shaped every project — Predictive Maintenance (cost of downtime vs. false alarm), Credit Risk (cost of FP vs. FN), Medical Diagnosis (cost of missed diagnosis).
- Strong mathematical foundation that translates directly to understanding optimizers, gradient descent, regularization, and loss-function design at the implementation level.

**Reflection:** Industrial engineering taught me that every optimization problem has constraints that aren't in the objective function — and ignoring them produces mathematically optimal solutions that fail in reality. That's exactly what happens with naive ML: you optimize accuracy and ship a model that's biased, brittle, or misaligned with business cost. My background means I default to the question that experienced ML engineers eventually learn the hard way: *what are you actually trying to minimize, and what does it cost when you're wrong?*