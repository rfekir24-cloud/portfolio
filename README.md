<div align="center">

# Redouan Fekir — Quantitative Finance & Machine Learning Portfolio

[![GitHub](https://img.shields.io/badge/GitHub-rfekir24--cloud-181717?style=for-the-badge&logo=github)](https://github.com/rfekir24-cloud)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/Machine_Learning-Scikit--Learn%20%7C%20NLP-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Econometrics](https://img.shields.io/badge/Econometrics-Event_Study%20%7C%20Time_Series-00599C?style=for-the-badge)](https://github.com/rfekir24-cloud)
[![Contact](https://img.shields.io/badge/Email-r.fekir24%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:r.fekir24@gmail.com)

*Quantitative Research • Natural Language Processing • Predictive Modeling • Financial Econometrics*

</div>

---

## Overview

Welcome to my project portfolio. My work focuses on **rigorous, leak-free empirical modeling** across financial markets and customer analytics—combining **Natural Language Processing (NLP)**, **out-of-sample time-series forecasting**, **high-frequency event studies**, and **interpretable machine learning pipelines**.

### Core Engineering & Research Principles
- **Strict Temporal Integrity:** Expanding walk-forward validation and percentile temporal cutoffs to prevent look-ahead bias and data leakage.
- **Econometric & Statistical Rigor:** HC3 heteroskedasticity-robust inference, futures-based policy surprise controls (`MP1`, `MP2`), probability calibration, and Brier score auditing.
- **Reproducible Architecture:** Modular Python packages, deterministic data pinning (commit hashes & file checksums), automated CLI pipelines, and unit/research-design test suites.

---

## Featured Projects

### 1. [Expected FOMC Tone and Market Reactions](https://github.com/rfekir24-cloud/fomc-tone-market-reactions)
> **Quantitative Macro & NLP Event Study** — Measuring whether financial markets react to the *unexpected* hawkish/dovish tone of Federal Reserve (FOMC) statements within a 30-minute intraday window.

[![Repo](https://img.shields.io/badge/Repository-fomc--tone--market--reactions-0969da?style=flat-square&logo=github)](https://github.com/rfekir24-cloud/fomc-tone-market-reactions)
![Python](https://img.shields.io/badge/Python-3.11+-blue?style=flat-square&logo=python)
![Domain](https://img.shields.io/badge/Domain-Monetary_Policy_%26_Asset_Pricing-success?style=flat-square)
![Methods](https://img.shields.io/badge/Methods-NLP_%7C_Walk--Forward_ML_%7C_Intraday_Event_Study-purple?style=flat-square)

#### Research Architecture
```mermaid
flowchart LR
    A["FOMC Statements\n& Macro Pre-Announcement\n(FRED, SPY, VIX, OIS)"] --> B["Tone Measurement\nDelta-Consistent Scoring (DCS)\n& FedNLP / Dictionary Benchmarks"]
    B --> C["Walk-Forward Forecasting\nPersistence, Ridge, ElasticNet,\nShallow Random Forest"]
    C --> D["Tone Innovation\ntone_innovation = actual - predicted"]
    D --> E["30-Min Intraday Event Study\nS&P 500, Treasury Yields, OIS\n(HC3 + MP1/MP2 Surprise Controls)"]
```

#### Key Highlights
- **Three-Stage Empirical Pipeline:**
  1. **Tone Quantification:** Continuous Delta-Consistent Scoring (`0 = dovish`, `1 = hawkish`) validated against FedNLP manual labels and transparent domain dictionaries (inflation, growth, policy stance).
  2. **Ex-Ante Tone Forecasting:** Expanding walk-forward out-of-sample predictions using only pre-announcement macro and market indicators (FRED policy rates, Treasury yields, VIX, broad dollar index, SPY momentum) to isolate true **tone innovations** ($\text{Tone Innovation}_t = \text{Actual Tone}_t - \widehat{\text{Expected Tone}}_t$).
  3. **High-Frequency Market Transmission:** 30-minute window regressions around FOMC releases using San Francisco Fed USMPD data (S&P 500, OIS, Treasury yields), controlling for futures-based monetary policy rate and path surprises (`MP1`, `MP2`) with HC3 robust standard errors.
- **Engineering Quality:** Full CLI package (`fomc-tone`), 5 modular research notebooks, YAML configuration + domain dictionaries, and 15+ unit & research-design tests verifying zero look-ahead leakage.

🔗 **[Explore Repository → `rfekir24-cloud/fomc-tone-market-reactions`](https://github.com/rfekir24-cloud/fomc-tone-market-reactions)**

---

### 2. [Online Retail Customer Engagement & 30-Day Retention Baseline](https://github.com/rfekir24-cloud/-Retail-Engagement-Project)
> **Predictive Customer Analytics & Explainable ML** — Leak-safe temporal pipeline predicting 30-day customer repurchase probability on the UCI Online Retail transactional dataset.

[![Repo](https://img.shields.io/badge/Repository---Retail--Engagement--Project-0969da?style=flat-square&logo=github)](https://github.com/rfekir24-cloud/-Retail-Engagement-Project)
![Python](https://img.shields.io/badge/Python-Scikit--Learn_%7C_SHAP-blue?style=flat-square&logo=python)
![Domain](https://img.shields.io/badge/Domain-Customer_Retention_%26_CLV-orange?style=flat-square)
![Methods](https://img.shields.io/badge/Methods-RFM_Engineering_%7C_Gradient_Boosting_%7C_Calibration-teal?style=flat-square)

#### Pipeline Architecture
```mermaid
flowchart LR
    A["Raw Transaction Logs\n(UCI Online Retail)"] --> B["Temporal Cutoff (P80)\nStrict History vs. 30-Day\nFuture Label Window"]
    B --> C["Customer Feature Store\nRFM, Basket Stats, Interpurchase\nIntervals, Cancellation Ratio"]
    C --> D["Model Training & Selection\nLogistic Regression &\nGradient Boosting Pipelines"]
    D --> E["Evaluation & Explainability\nROC-AUC, PR-AUC, F1 Threshold,\nCalibration, Brier Score & SHAP"]
```

#### Key Highlights
- **Leak-Safe Temporal Split:** Uses the 80th percentile of `InvoiceDate` as a strict temporal cutoff—aggregating customer behavior strictly prior to the cutoff and labeling non-cancelled purchases in the subsequent `(cutoff, cutoff + 30 days]` window.
- **Rich Behavioral Feature Engineering:** Constructs customer-level Recency, Frequency, Monetary (RFM) metrics, basket size distributions, unique product diversity, unit-price statistics, interpurchase time intervals, and invoice cancellation ratios.
- **Calibrated Decisioning & Explainability:** Evaluates models across ROC-AUC, PR-AUC, optimal F1 precision-recall thresholds, reliability calibration curves, and Brier scores, paired with coefficient inspection, tree feature importances, and SHAP values.

🔗 **[Explore Repository → `rfekir24-cloud/-Retail-Engagement-Project`](https://github.com/rfekir24-cloud/-Retail-Engagement-Project)**

---

## Project Comparison Matrix

| Dimension | [Expected FOMC Tone & Market Reactions](https://github.com/rfekir24-cloud/fomc-tone-market-reactions) | [Online Retail Engagement Baseline](https://github.com/rfekir24-cloud/-Retail-Engagement-Project) |
| :--- | :--- | :--- |
| **Primary Domain** | Quantitative Macroeconomics, Monetary Policy, Asset Pricing | E-Commerce Analytics, Customer Retention, Behavioral Modeling |
| **Core Problem** | Do intraday equity & rate markets price *unexpected* FOMC statement tone? | Will an active customer complete a non-cancelled purchase in the next 30 days? |
| **Data Sources** | Federal Reserve, SF Fed USMPD (30-min intraday), FRED, Yahoo Finance, DCS, FedNLP | UCI Online Retail Transaction Logs |
| **Validation Strategy** | Expanding walk-forward time-series window | Temporal cutoff (80th percentile) + stratified customer holdout |
| **Models & Methods** | NLP Scoring (DCS/FedNLP), Ridge, ElasticNet, Random Forest, OLS with HC3 SEs | Logistic Regression, Gradient Boosting, Probability Calibration, SHAP |
| **Key Evaluation Metrics** | Out-of-sample MAE, $R^2$, HC3 $t$-stats, MP1/MP2 controlled $\beta$ | ROC-AUC, PR-AUC, Optimal F1 Threshold, Brier Score, Reliability Curve |

---

## Technical Stack

| Category | Tools & Libraries |
| :--- | :--- |
| **Languages** | Python 3.11+, SQL, Bash, Markdown / LaTeX |
| **Data & Econometrics** | `pandas`, `numpy`, `statsmodels` (HC3 robust inference, time-series regressions), `scipy` |
| **Machine Learning & NLP** | `scikit-learn` (Ridge, ElasticNet, Random Forest, Gradient Boosting, Calibration), `shap`, Delta-Consistent Scoring (DCS), FedNLP |
| **Visualization & Reporting** | `matplotlib`, `seaborn`, Jupyter Notebooks, automated Markdown/LaTeX table generation |
| **Software Engineering** | `pytest`, `pyproject.toml` packaging, CLI tooling (`argparse`/`typer`), Git, reproducible shell pipelines |

---

## Repository Contents

- [`README.md`](README.md) — Complete portfolio overview, project architecture diagrams, and links.
- [`index.html`](index.html) & [`assets/`](assets/) — Responsive, interactive web portfolio showcase (ready for GitHub Pages or local viewing).

---

<div align="center">

**Redouan Fekir** • [GitHub `@rfekir24-cloud`](https://github.com/rfekir24-cloud) • [r.fekir24@gmail.com](mailto:r.fekir24@gmail.com)

</div>
