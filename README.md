Datenanalyse
Python-Programmierung
Technische Schulung und Mentoring

# Project: YouTube Channel Growth Analytics

This project is an end-to-end data science study aimed at optimizing a YouTube channel's growth strategy using data analysis and machine learning. The primary goal is to enable the channel to meet the **YouTube Partner Program (YPP)** eligibility requirements: **1,000 subscribers and 4,000 hours of watch time**.

---

## 🎯 Business Goal & Objective

For YouTube content creators, enabling monetization is a critical step toward sustainability. The core business objective of this project is to reach the YPP goals within a 6-month timeframe by allocating limited resources (time, production effort) to the most effective content strategies. The analysis aims to make key decisions—such as what content to produce, how to optimize it, and when to publish—entirely data-driven.

---

## 🛠️ Tech Stack & Tools

- **Programming Language:** Python 3.9+
- **Libraries:**
  - **Data Manipulation:** Pandas, NumPy
  - **Data Visualization:** Matplotlib, Seaborn
  - **Machine Learning:** Scikit-learn, XGBoost
  - **API Interaction:** google-api-python-client, google-auth-oauthlib
  - **NLP:** VADER Sentiment
- **Environment:** Jupyter Notebook, VS Code
- **Data Source:** YouTube Analytics API, YouTube Data API v3
- **Reporting:** Google Looker Studio / Tableau

---

## 📁 Project Structure

```
├── data/
│   ├── raw/              # Raw data fetched from API (CSV)
│   └── processed/        # Cleaned, merged, and processed datasets
├── notebooks/
│   ├── 01_Data_Acquisition.ipynb
│   ├── 02_Exploratory_Data_Analysis.ipynb
│   ├── 03_Predictive_Modeling.ipynb
│   └── 04_Unsupervised_Learning.ipynb
├── scripts/
│   └── youtube_api_utils.py # Helper functions for API connection
├── requirements.txt         # Required Python libraries for the environment
└── README.md                # This project documentation
```

---

## 🚀 Project Phases & Methodology

The project is divided into 4 key phases using an Agile methodology with 2-week sprints. Each phase is designed to meet a set of pre-defined acceptance criteria.

### Phase 1: Data Acquisition & Exploratory Data Analysis (EDA)

The goal of this phase is to establish a reliable data collection pipeline and conduct foundational exploratory data analysis to understand the channel's historical performance.

**Key Activities:**
- Completing the authentication process for the YouTube APIs.
- Fetching channel and video-level metrics via the API.
- Performing data cleaning, transformation, and merging.
- Visualizing the trends of Key Performance Indicators (KPIs) over time.

**✅ Acceptance Criteria:**
- **AC 1.1:** A repeatable Python script exists that fetches all required metrics (views, watch time, subscribers, demographics, traffic sources) and saves them as CSV files.
- **AC 1.2:** A master DataFrame is created for analysis, with corrected data types, handled missing values, and a documented schema.
- **AC 1.3:** An EDA notebook is completed, containing key visualizations and statistical summaries that illustrate the channel's overall growth trends, video performance distribution, and outliers.

### Phase 2: Deep-Dive Analysis & Insight Generation

This phase transitions from asking "what is happening?" to "why is it happening?" by uncovering the core dynamics driving channel performance.

**Key Activities:**
- Segmenting videos into performance tiers (e.g., top, average, bottom performers).
- Analyzing the common characteristics (topic, duration, publish time) of successful videos.
- Examining Audience Retention graphs to identify critical viewer drop-off points.
- Analyzing the impact of different traffic sources on subscriber gain and watch time.

**✅ Acceptance Criteria:**
- **AC 2.1:** The categories, formats, and durations of videos that generate the most subscribers and watch time are clearly documented.
- **AC 2.2:** At least three actionable, data-backed insights that can directly influence the channel's content strategy have been generated.
- **AC 2.3:** A primary, testable growth hypothesis has been formulated (e.g., "Focusing on X format and Y topic will accelerate subscriber growth").

### Phase 3: Predictive Modeling (Performance Forecasting)

In this phase, a machine learning model was developed to predict the potential performance of a video concept before it is produced.

**Key Activities:**
- Defining the prediction target (e.g., `views_first_7_days`).
- Engineering a feature set from pre-publication metadata (duration, category, title length, etc.).
- Training and evaluating a baseline model and several regression models (e.g., Random Forest, XGBoost).
- Conducting feature importance analysis to understand which factors are most predictive of performance.

**✅ Acceptance Criteria:**
- **AC 3.1:** The final regression model significantly outperforms the simple baseline model on a chosen evaluation metric (e.g., Mean Absolute Error - MAE).
- **AC 3.2:** The top 5 most important features that drive the model's predictions are identified, and their impact on performance is interpreted.
- **AC 3.3:** The model's predictive power, key metrics (R², RMSE), and limitations are clearly documented.

### Phase 4: Unsupervised Learning (Content & Audience Segmentation)

This phase uses unsupervised learning techniques to discover hidden structures within the content library and understand audience feedback at scale.

**Key Activities:**
- Applying the K-Means clustering algorithm to group videos based on their performance metrics.
- Analyzing and profiling the resulting video clusters (e.g., "High-Engagement Tutorials," "Viral Shorts").
- Performing sentiment analysis on comments from popular videos using Natural Language Processing (NLP).

**✅ Acceptance Criteria:**
- **AC 4.1:** At least three distinct and meaningful video clusters are identified that can inform the channel's content strategy (e.g., which content pillars to focus on).
- **AC 4.2:** Sentiment analysis of comments provides a quantitative measure of audience reception for different video clusters or topics.
- **AC 4.3:** New strategic opportunities (e.g., "niche topics loved by the core community") are derived from the clustering and NLP results.

## 💡 Future Work

- **A/B Testing Framework:** Design a framework to systematically test hypotheses generated from the analysis (e.g., testing different thumbnail styles or title formats to improve CTR).
- **Time-Series Forecasting:** Develop a time-series model (e.g., Prophet or ARIMA) to forecast future channel growth and set more dynamic performance targets.
