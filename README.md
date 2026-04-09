# Privacy-Preserving Synthetic Data for Retail Demand Forecasting

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19479285.svg)](https://doi.org/10.5281/zenodo.19479285)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the code for an end-to-end, privacy-preserving retail demand forecasting pipeline. It generates controllable synthetic SKU-level data to bypass real-world data privacy constraints (GDPR), engineers leakage-safe features, and benchmarks tree-based ensembles (Random Forest, LightGBM) using Rolling-Origin Cross-Validation (ROCV).

Read the full preprint here: [Zenodo DOI: 10.5281/zenodo.19479285](https://doi.org/10.5281/zenodo.19479285)

##  Key Features
* **Controllable Synthetic Generator:** Simulates Poisson base demand, daily/weekly seasonality, promotional uplifts, and exogenous traffic across 100 SKUs and 60 days.
* **Leakage-Safe Feature Engineering:** Implements time-aware lags and rolling statistics.
* **Robust Evaluation:** Time-ordered splits and ROCV, preventing temporal leakage.
* **Interactive Dashboard:** Includes a Streamlit prototype for real-time scenario testing.

##  Methodology (FUP Framework)
This project is built around the **Fidelity-Utility-Privacy (FUP)** trade-off:
1. **Fidelity:** Verified via Autocorrelation (ACF) peaks at 24h/168h and STL decomposition.
2. **Utility:** Random Forest achieved MAPE of 11.7% on short-horizon (1-3 day) forecasts.
3. **Privacy:** 100% synthetic generation ensures zero exposure of Personally Identifiable Information (PII) or proprietary sales records (Privacy-by-Simulation).

##  PhD Research Extension
This codebase serves as the baseline for a proposed PhD project extending this work to:
1. Introduce formal **Differential Privacy (DP)** during generator parameter estimation.
2. Evaluate empirical privacy risks via **Membership Inference Attacks**.
3. Scale the pipeline for energy/smart-grid forecasting using High-Performance Computing (HPC).

*(Developed as part of an MSc Data Science project at the University of Greenwich).*
