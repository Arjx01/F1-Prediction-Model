# F1 Prediction Model

A machine learning pipeline that predicts Formula 1 race times using historical race data and current qualifying results. Built as a personal project to apply regression modeling to real-world, messy sports data.

## Overview

This project pulls historical Formula 1 data via the [FastF1](https://docs.fastf1.dev/) API — lap times, race results, and telemetry — combines it with 2024 season results and 2025 qualifying data, and trains a model to predict race outcomes for the 2025 season.

## Features

- Automated data collection from FastF1 (lap times, race results, telemetry)
- Feature engineering from qualifying position, historical driver/team performance, and race-specific variables
- Gradient Boosting Regressor model trained to predict race times
- Per-Grand-Prix prediction scripts — one script per race weekend
- Model evaluation using Mean Absolute Error (MAE)

## Tech Stack

- **Python**
- **FastF1** — historical and live F1 timing/telemetry data
- **scikit-learn** — Gradient Boosting Regressor, model evaluation
- **pandas / numpy** — data processing and feature engineering

## Project Structure

```
F1-Prediction-Model/
├── prediction1.py      # Australian GP
├── prediction2.py      # [next race in season order]
├── ...                 # one script per Grand Prix
├── requirements.txt
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.9+
- pip

### Installation

```bash
git clone https://github.com/Arjx01/F1-Prediction-Model.git
cd F1-Prediction-Model
pip install -r requirements.txt
```

### Usage

Run the prediction script for a given race weekend:

```bash
python prediction1.py
```

Each script fetches the relevant historical and qualifying data, trains the model on prior race results, and outputs predicted finishing times for the selected Grand Prix.

## Model & Evaluation

The model is a **Gradient Boosting Regressor** trained on 2024 race results and evaluated on held-out data using **Mean Absolute Error (MAE)**. On test runs, the model achieved an MAE of approximately **[X] seconds** — meaning predicted race times were off by about that margin on average compared to actual results.

*(Update the MAE figure above with your actual, current result before sharing this repo — I've left it as a placeholder since I don't want to state a number you haven't verified yourself.)*

## What I Learned

- Working with real-world, session-based sports telemetry data and the quirks of the FastF1 API
- Feature engineering for regression tasks (qualifying position, team/driver historical form)
- Evaluating regression models with MAE rather than classification metrics
- Structuring a project around per-event prediction scripts

## Future Improvements

- [ ] Incorporate weather and track condition data
- [ ] Experiment with additional models (XGBoost, Random Forest) for comparison
- [ ] Add automated data refresh before each race weekend
- [ ] Build a simple web interface to view predictions without running scripts manually

## Disclaimer

This is a personal learning project and is not affiliated with Formula 1, FIA, or any F1 team. Predictions are for educational purposes only.

## License

[Add a license if you want one — MIT is a common, permissive choice for personal/learning projects.]
