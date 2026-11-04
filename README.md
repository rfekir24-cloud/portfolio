<div align="center">

<img src="assets/profile.png" alt="Redouan FEKIR" width="130" style="border-radius: 50%;" />

# Redouan FEKIR — Portfolio Ingénierie Financière de Marché, Quant & Data

**Master 2 Ingénierie Financière de Marché – Université de Lorraine (Metz, France)**

[![Site Web Portfolio](https://img.shields.io/badge/Site_Web_Portfolio-rfekir24--cloud.github.io-0284c7?style=for-the-badge&logo=google-chrome&logoColor=white)](https://rfekir24-cloud.github.io/portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Redouan_FEKIR-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/redouanfekir-rf/)
[![CV PDF](https://img.shields.io/badge/CV_Complet-Télécharger_PDF-10b981?style=for-the-badge&logo=adobe-acrobat-reader&logoColor=white)](https://rfekir24-cloud.github.io/portfolio/assets/Redouan_FEKIR_CV.pdf)
[![Email](https://img.shields.io/badge/Email-fekir.redouan%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:fekir.redouan@gmail.com)

📍 Metz, France • 📞 +33 (0)7 54 59 06 33 • 🌐 **[Accéder au site web interactif du Portfolio](https://rfekir24-cloud.github.io/portfolio/)**

</div>

---

## À propos

Étudiant en **Master 2 Ingénierie Financière de Marché** à l'**Université de Lorraine**, je me spécialise dans la **finance quantitative de marché**, l'**économétrie des séries temporelles financières** et la **Data Science / Machine Learning appliqué**. Mes travaux allient rigueur économétrique, absence stricte de biais d'anticipation (*look-ahead bias*) et automatisation de pipelines analytiques (Python, SQL, RStudio, EViews, Power BI).

---

## Projets GitHub & Code

### 1. [Expected FOMC Tone & Réactions de Marché](https://github.com/rfekir24-cloud/fomc-tone-market-reactions)
> **Macro-Finance Quantitative, NLP & Étude d'Événements Intrajournalière (30 min)**

[![Repo](https://img.shields.io/badge/Dépôt_GitHub-fomc--tone--market--reactions-0969da?style=flat-square&logo=github)](https://github.com/rfekir24-cloud/fomc-tone-market-reactions)
![Python](https://img.shields.io/badge/Python-3.11+-blue?style=flat-square&logo=python)
![Domaine](https://img.shields.io/badge/Domaine-Politique_Monétaire_%26_Marchés_de_Taux-success?style=flat-square)

```mermaid
flowchart LR
    A["Communiqués FOMC\n& Données Pré-Annonce\n(FRED, SPY, VIX, OIS)"] --> B["Mesure du Ton (NLP)\nDelta-Consistent Scoring (DCS)\n& FedNLP / Dictionnaires"]
    B --> C["Prévision Walk-Forward\nPersistance, Ridge, ElasticNet,\nRandom Forest"]
    C --> D["Innovation de Ton\ntone_innovation = actual - predicted"]
    D --> E["Event Study 30-Min\nS&P 500, Treasuries, OIS\n(HC3 + Surprises MP1/MP2)"]
```

- **Mesure du ton monétaire :** Score continu Delta-Consistent Scoring (`0 = dovish`, `1 = hawkish`) validé face aux annotations FedNLP et à des dictionnaires transparents.
- **Prévision hors-échantillon (Walk-Forward) :** Prédiction du ton attendu uniquement avec l'information disponible avant l'annonce (taux FRED, VIX, rendements obligataires, dollar, SPY) afin d'isoler l'**innovation de ton** ($\text{Tone Innovation}_t = \text{Actual Tone}_t - \widehat{\text{Expected Tone}}_t$).
- **Transmission de marché à 30 minutes :** Régressions haute fréquence sur les données SF Fed USMPD (S&P 500, OIS, Treasuries) avec erreurs standards robustes HC3 et contrôle des surprises de taux à terme (`MP1`, `MP2`).

🔗 **[Voir le dépôt → `rfekir24-cloud/fomc-tone-market-reactions`](https://github.com/rfekir24-cloud/fomc-tone-market-reactions)**

---

### 2. [Prédiction de l'Engagement Client à 30 Jours (Online Retail)](https://github.com/rfekir24-cloud/-Retail-Engagement-Project)
> **Machine Learning Prédictif, Feature Engineering Comportemental & Explicabilité SHAP**

[![Repo](https://img.shields.io/badge/Dépôt_GitHub---Retail--Engagement--Project-0969da?style=flat-square&logo=github)](https://github.com/rfekir24-cloud/-Retail-Engagement-Project)
![Python](https://img.shields.io/badge/Python-Scikit--Learn_%7C_SHAP-blue?style=flat-square&logo=python)
![Domaine](https://img.shields.io/badge/Domaine-Scoring_Client_%26_Rétention-orange?style=flat-square)

```mermaid
flowchart LR
    A["Transactions Brutes\n(UCI Online Retail)"] --> B["Coupure Temporelle (P80)\nHistorique Strict vs. Fenêtre\nCible à 30 Jours"]
    B --> C["Variables Comportementales\nRFM, Panier, Intervalles\nInter-Achats, Taux d'Annulation"]
    C --> D["Modélisation ML\nRégression Logistique &\nGradient Boosting"]
    D --> E["Évaluation & Explicabilité\nROC-AUC, PR-AUC, Seuil F1,\nCalibration, Score de Brier & SHAP"]
```

- **Séparation temporelle sans fuite (*Leak-Safe*) :** Utilisation du 80<sup>e</sup> centile de `InvoiceDate` comme date de coupure pour construire l'historique client et prédire le réachat non annulé sur `(cutoff, cutoff + 30 jours]`.
- **Modélisation calibrée :** Comparaison Régression Logistique vs. Gradient Boosting (ROC-AUC, PR-AUC, seuil F1 optimal, courbe de calibration, score de Brier) et interprétation via **SHAP**.

🔗 **[Voir le dépôt → `rfekir24-cloud/-Retail-Engagement-Project`](https://github.com/rfekir24-cloud/-Retail-Engagement-Project)**

---

## Thèse & Projets Académiques

- **Thèse de Master 2 IFM (Université de Lorraine) :** *Analyse quantitative et comparative des indicateurs de performance et de risque des ETF Sectoriels par rapport aux ETF Indiciels.*
- **Économétrie des Séries Temporelles (Université de Lorraine) :** *Analyse de l'impact du taux effectif des Fonds Fédéraux (FFER) sur le crédit, l'investissement et la stabilité financière mondiale à l'aide de modèles ARIMA et VAR et prévisions de volatilité via ARCH/GARCH.*
- **Étude de Recherche et d'Analyse (Université de Lorraine) :** *L'impact de la directive CSRD (Corporate Sustainability Reporting Directive) sur la performance financière des entreprises européennes.*

---

## Expériences Professionnelles

| Période | Poste | Entreprise & Lieu | Missions clés |
| :--- | :--- | :--- | :--- |
| **Janv. 2026 – Juin 2026** | **Analyste Investigations Criminalité Financière & Économique** | **Attijariwafa bank** (Casablanca, Maroc) | Surveillance des transactions (100+ flux), détection blanchiment/fraude (30+ dossiers clients), revues AML/KYC (100+ profils), échanges autorités (5+ cas/j) et 10+ rapports de direction. |
| **Mars 2025 – Juil. 2025** | **Assistant Data / Business Analyst – Automatisation & Reporting** | **TechIndus Solutions** (Strasbourg, France) | Automatisation du traitement de données de production (**Python, SQL**), dashboards interactifs **Power BI** (OEE, arrêts machine, taux de défaut), gestion de projet métier/technique. |
| **Sept. 2024 – Aujourd'hui** | **Employé Polyvalent de Magasin** | **LIDL FRANCE** (Metz, France) | Approvisionnement, gestion de la qualité, contrôle du respect des procédures et normes légales. |
| **Avril 2022 – Juin 2022** | **Stage de Recherche** | **GATE – CNRS (UMR5824)** (Saint-Étienne, France) | Étude sur l'évolution de la **Blockchain** : expansion de la *Proof of Stake (PoS)* et mesures de sécurité face à la criminalité dans l'univers des cryptomonnaies. |
| **Juin 2021 – Août 2021** | **Assistant Chargé d'Affaires Entreprises** | **Banque Centrale Populaire – Centre d'Affaires** (Oujda, Maroc) | Gestion d'un portefeuille corporate international, analyse du risque, revue **KYC**, montage de dossiers de crédit et suivi des flux. |
| **Janv. 2021 – Mars 2021** | **Assistant Comptable et Financier** | **Fiduciaire TIB COMPT** (Oujda, Maroc) | Opérations comptables, élaboration du bilan, analyse financière et conformité fiscale. |

---

## Formation

- **2023 – 2026 | Master 2 IFM – Ingénierie Financière de Marché** — *Université de Lorraine (Metz, France)*
  - Évaluation des actifs financiers, Modèles stochastiques pour la finance de marché, Théorie de la finance, Économétrie des séries temporelles financières, Gestion de portefeuille, Options et produits dérivés, Enjeux réglementaires en finance.
- **2022 – 2023 | Master 1 Analyse et Politique Économique** — *Université Jean Monnet – Saint-Etienne School of Economics (Saint-Étienne, France)*
  - Data Management & Information Systems, Économétrie d'évaluation des programmes, Économie monétaire et bancaire, Théorie des graphes, Théorie de la décision.
- **2018 – 2022 | Licence en Économie Appliquée** — *Université Jean Monnet – IAE Saint-Etienne (Saint-Étienne, France)*
  - Économétrie, Statistique Inférentielle, Business Intelligence, Finance Internationale, Finance d'entreprise, Recherche Opérationnelle.

---

## Compétences & Langues

- **Programmation, Économétrie & BI :** Python, SQL, RStudio, EViews, VBA, Power BI, Tableau, LaTeX, SAP BO, ODOO, Office 365
- **Langues :** Français (Courant) • Anglais (Courant) • Arabe (Langue maternelle)
- **Activités :** Musculation, Natation, Volontariat, Sports Automobiles
