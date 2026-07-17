# Customer Churn Analysis — Telecommunications Company

Data analytics project: preprocessing, customer segmentation (clustering), and (upcoming) churn
prediction using an Artificial Neural Network, for a telecom customer dataset.

## Project Stages

- [x] **Stage 2.1 — Data Preparation**: load data, integrity checks, encode categorical variables,
      feature scaling, train/test split.
- [x] **Stage 2.2 — Clustering Analysis**: optimal k via elbow method + silhouette score, KMeans
      model, PCA visualisation, labelled cluster interpretation.
- [ ] **Stage 3.1 — Predictive Modeling (ANN)**: churn prediction model.
- [ ] **Stage 3.2 — Final Report**: findings, retention recommendations, limitations.

## Repository Structure

```
.
├── Dataset_ATS_v2.csv       # source dataset
├── churn_analysis.ipynb     # main notebook (data prep + clustering)
├── requirements.txt         # Python dependencies
└── README.md
```

## Dataset

`Dataset_ATS_v2.csv` — 7,043 customer records with the following columns: `gender`,
`SeniorCitizen`, `Dependents`, `tenure`, `PhoneService`, `MultipleLines`, `InternetService`,
`Contract`, `MonthlyCharges`, `Churn`.

## Setup

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook churn_analysis.ipynb
```

## Key Findings So Far

Clustering on the encoded/scaled features identified **3 customer segments**, driven mainly by
**contract type**:

| Cluster | Segment | Churn Rate |
|---|---|---|
| 0 | Two-Year Contract | 25.4% |
| 1 | Month-to-Month | **27.3% (highest)** |
| 2 | One-Year Contract | 25.8% |

Month-to-month customers are the priority segment for retention efforts.

## Author

_Add your name here._
