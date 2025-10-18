# YouTube Channel Growth Analytics

One-line: End-to-end data science pipeline to analyze YouTube channel performance and generate actionable recommendations.

Quick Links
- Notebooks: notebooks/
- Data: data/
- Scripts: scripts/
- Requirements: requirements.txt

Table of Contents
- About
- Quickstart
- Tech Stack
- Project Structure
- Run Order
- Config / Credentials
- Usage / Example results
- Contributing
- License
- Contact

About
This repository contains a repeatable pipeline and notebooks to:
- Fetch YouTube Analytics & Data API metrics
- Perform EDA and generate insights for content strategy
- Train predictive models and run clustering + sentiment analysis

Quickstart (minimum steps)
1. Clone repository:
   git clone https://github.com/eboekenh/youtube-growth-analytics.git
2. Create virtual environment and install:
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   OR
   conda env create -f environment.yml
3. Add credentials (see Config / Credentials below).
4. Run a smoke test (fetch a small dataset):
   python scripts/youtube_api_utils.py --fetch-sample --out data/raw/sample.csv
   OR open notebooks/01_Data_Acquisition.ipynb and run the first cells.

Tech Stack
- Python 3.9+
- pandas, numpy, matplotlib, seaborn
- scikit-learn, xgboost
- google-api-python-client, google-auth-oauthlib
- VADER for sentiment analysis
- Jupyter Notebooks, VS Code

Project Structure
```
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── 01_Data_Acquisition.ipynb
│   ├── 02_Exploratory_Data_Analysis.ipynb
│   ├── 03_Predictive_Modeling.ipynb
│   └── 04_Unsupervised_Learning.ipynb
├── scripts/
│   └── youtube_api_utils.py
├── requirements.txt
├── environment.yml
└── README.md
```

Run Order / Notebooks
1. notebooks/01_Data_Acquisition.ipynb — fetch and save raw CSVs to data/raw/
2. notebooks/02_Exploratory_Data_Analysis.ipynb — cleaning and EDA (use data/processed/master.csv)
3. notebooks/03_Predictive_Modeling.ipynb — feature engineering & modeling
4. notebooks/04_Unsupervised_Learning.ipynb — clustering & sentiment

Config / Credentials
- Create OAuth 2.0 credentials in Google Cloud and download credentials.json OR use a service account as needed.
- Save the file to: ./credentials/credentials.json
- Or set env var: export YT_CREDENTIALS="./credentials/credentials.json"
- Do NOT commit credentials to git. Use .gitignore (see .gitignore example).

Example environment variables (.env or export)
- YT_CREDENTIALS=./credentials/credentials.json
- DATA_DIR=./data
- LOG_LEVEL=INFO

Usage / Example results
- Add screenshots/plots or a short summary of key model metrics (e.g., MAE, RMSE, top features). Place example images in docs/ or images/ and reference here.

Security & Data Privacy
- Never commit credentials or Personally Identifiable Information (PII).
- Use environment variables or secret managers for credentials.
- Strip or anonymize user data before publishing datasets.

Contributing
- See CONTRIBUTING.md for coding style and PR process.
- Use feature branches, run linters, and add brief descriptions to PRs.

License
- See LICENSE (MIT recommended).

Contact
- Repo owner: @eboekenh