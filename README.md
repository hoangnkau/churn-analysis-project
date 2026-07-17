# Customer Churn Analysis — Telecommunications Company

Data analytics project: preprocessing, customer segmentation (clustering), and churn prediction
(Artificial Neural Network) for a telecom customer dataset — including a final retention strategy
report for stakeholders.

## Project Deliverables Status

- [x] **Stage 1.1 — Project Charter**: [`docs/Project_Charter.docx`](docs/Project_Charter.docx)
- [x] **Stage 2.1 — Data Preparation**: load data, integrity checks, encode categorical variables,
      feature scaling, train/test split.
- [x] **Stage 2.2 — Clustering Analysis**: optimal k via elbow method + silhouette score, KMeans
      model, PCA visualisation, labelled cluster interpretation.
- [x] **Stage 3.1 — Predictive Modeling (ANN)**: architecture, training, evaluation, feature importance.
- [ ] **Stage 3.2 — Final Report**: findings, retention recommendations, limitations. *(in progress)*

## Repository Structure

```
.
├── data/
│   └── Dataset_ATS_v2.csv              # source dataset
├── notebooks/
│   ├── 01_data_prep_clustering.ipynb   # Stage 2.1 + 2.2
│   └── 02_ann_churn_prediction.ipynb   # Stage 3.1
├── docs/
│   ├── Project_Charter.docx            # Stage 1.1
│   └── Final_Report.docx               # Stage 3.2 (coming soon)
├── requirements.txt
├── .gitignore
└── README.md
```

## Dataset

`Dataset_ATS_v2.csv` — 7,043 customer records: `gender`, `SeniorCitizen`, `Dependents`, `tenure`,
`PhoneService`, `MultipleLines`, `InternetService`, `Contract`, `MonthlyCharges`, `Churn`.

## Setup

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/01_data_prep_clustering.ipynb
```

## Key Findings So Far

### Clustering (Stage 2.2)
3 customer segments identified, driven mainly by **contract type**:

| Cluster | Segment | Churn Rate |
|---|---|---|
| 0 | Two-Year Contract | 25.4% |
| 1 | Month-to-Month | **27.3% (highest)** |
| 2 | One-Year Contract | 25.8% |

### Predictive Model (Stage 3.1)
A feed-forward ANN (16 → 8 → 1 units, dropout regularisation, class-weighted for the ~26.5% churn
imbalance) was trained to predict churn:

| Metric | Score |
|---|---|
| Accuracy | 0.712 |
| Precision | 0.473 |
| Recall | 0.743 |
| F1 Score | 0.578 |
| ROC-AUC | 0.806 |

Recall was prioritised over raw accuracy — missing an at-risk customer costs more to the business
than a false alarm. Permutation feature importance is used to identify which attributes the model
relies on most (see notebook for the ranked chart).

## Author

_Add your name here._
