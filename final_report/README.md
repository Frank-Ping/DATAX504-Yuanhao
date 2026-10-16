# DATAX504 Final Project: Six-Hour-Ahead Temperature Forecasting

Forecast air temperature six hours ahead from the previous 24 hours of weather observations (MPI-BGC Jena roof station, 2018–2025). The project compares a persistence baseline with Dense and GRU networks that use temperature only or four inputs (temperature, pressure, humidity, wind speed), and includes an error analysis and a feature ablation study.

All code is in `final_project.ipynb`. The report is `fp_final_Ping_Yuanhao.pdf` (submitted on Moodle).

## Setup

Python 3 with:

```
pip install tensorflow==2.21.0 keras==3.15.1 numpy pandas matplotlib truststore jupyter
```

## Data

The notebook downloads the weather data automatically from the MPI-BGC Jena weather station archive (https://www.bgc-jena.mpg.de/wetter/) into `data/` the first time it runs. Splits by target year: train 2018–2023, validation 2024, test 2025.

## How to run

Open `final_project.ipynb` and choose **Run All**. The `RETRAIN` flag in section 1 controls the run mode:

- `RETRAIN = True`: full run from scratch, including training and the feature ablation (about 45 minutes on a CPU).
- `RETRAIN = False`: no training. Reloads the saved models in `models/` and the saved results in `outputs/` and redraws all tables and figures (about 2–3 minutes).

Training is deterministic (seed 504, TensorFlow op determinism), so both modes give the same numbers.

## Folders

- `data/`: downloaded raw data (not committed)
- `models/`: trained models
- `outputs/`: result tables (CSV/JSON); `outputs/feature_ablation/` holds the ablation runs
- `figures/`: figures used in the report
