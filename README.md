# ecl-credit-risk-lending-club

ECL / PD-LGD-EAD credit-risk model on Lending Club data (IFRS 9 / Ind AS 109 framing).



\# ECL / PD-LGD-EAD Credit Risk Model (Lending Club)



An expected credit loss (ECL) model on the public Lending Club dataset, covering the

three IFRS 9 / Ind AS 109 risk parameters — Probability of Default (PD), Loss Given

Default (LGD), and Exposure at Default (EAD) — with 12-month and lifetime PD staging.



\## Context

This project builds the Advanced-IRB parameter set (PD, LGD, EAD) using the Basel

framing from the source course. In the Indian regulatory context these map to

IFRS 9 / Ind AS 109 expected credit loss provisioning rather than regulatory capital,

since the RBI implements the Standardised Approach only for credit risk

(Credit Risk – Standardised Approach Directions, 2026; effective 1 April 2027) and

does not permit internal-ratings-based (IRB) approaches.



Expected Loss:  EL = PD x LGD x EAD



\## Structure

\- data/raw/        raw Lending Club data (git-ignored; see Data below)

\- data/processed/  cleaned/derived datasets (git-ignored)

\- notebooks/       exploratory analysis

\- src/             reusable functions (prep, modelling, evaluation)

\- outputs/         charts and model artifacts



\## Data

The raw Lending Club dataset is not committed (size + licensing). Download it and

place it in data/raw/.



\## Setup

python -m venv .venv

.\\.venv\\Scripts\\Activate.ps1

pip install -r requirements.txt



\## Status

Work in progress — building PD -> LGD -> EAD -> Expected Loss.



Decision Note: 

"Used the full Lending Club accepted-loans dataset (\~2.26M rows, 145 columns). Chose the complete file to work with real-world scale and messiness; core modelling columns are present across all dataset vintages, so extra fields are dropped during preprocessing. Note: full-size file has memory implications for later binning/fitting steps."

