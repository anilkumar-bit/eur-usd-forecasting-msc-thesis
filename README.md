# EUR/USD Forecasting Using ARIMA, Random Forest and LSTM

This repository contains the implementation developed for an MSc thesis comparing three forecasting approaches for weekly EUR/USD exchange-rate prediction:

- ARIMA
- Random Forest
- Long Short-Term Memory (LSTM)

The models are evaluated under a common forecasting framework using the same dataset, forecasting horizon and evaluation metrics.

## Project Objective

The objective of this project is to compare traditional statistical, machine-learning and deep-learning approaches for one-week-ahead EUR/USD forecasting.

The study uses weekly EUR/USD data covering the period from 2000 to 2026.

## Forecasting Models

### ARIMA
A traditional statistical time-series forecasting model based on the Box-Jenkins approach.

### Random Forest
A machine-learning regression model using historical and engineered predictor variables.

### LSTM
A recurrent neural-network model designed for sequential data. The LSTM uses sequences of the previous five weekly observations to predict the next week's EUR/USD value.

## Data

The `data` directory contains:

- `data/raw/` - original EUR/USD datasets
- `data/processed/` - cleaned and model-ready datasets

The final model-ready dataset used in the forecasting models is:

`eur_weekly_model_ready_v2.csv`

The dataset includes historical EUR/USD information and engineered features such as:

- Lagged values
- Moving averages
- Rolling volatility
- Historical Open, High, Low and percentage-change information

The forecasting target represents the EUR/USD value one week ahead.

## Notebook Structure

The notebooks should be followed in this order:

1. `01_data_exploration.ipynb`  
   Exploratory data analysis and initial data preparation.

2. `02_preprocessing.ipynb`  
   Data cleaning, target construction and feature engineering.

3. `03_arima.ipynb`  
   ARIMA model development and evaluation.

4. `04_random_forest.ipynb`  
   Random Forest model development and evaluation.

5. `05_lstm.ipynb`  
   LSTM model development, training and evaluation.

## Evaluation Metrics

Model performance is evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)

## Final Model Results

| Model | MAE | RMSE | MAPE |
|---|---:|---:|---:|
| ARIMA | 0.112185 | 0.126222 | 10.42% |
| Random Forest | 0.017139 | 0.021443 | 1.58% |
| LSTM | 0.028196 | 0.034645 | 2.62% |

Within this experimental framework, Random Forest achieved the lowest forecasting errors, followed by LSTM and ARIMA.

These results are specific to the dataset, forecasting horizon, predictor variables and modelling procedure used in this project and should not be interpreted as evidence that one method is universally superior.

## Reproducibility

The project uses a chronological train-test procedure rather than random shuffling.

For the LSTM model:

- Sequence length: 5 weeks
- Random seed: 42
- Epochs: 50
- Batch size: 16
- Validation split: 0.2
- Training shuffling disabled

Feature scaling for the LSTM is fitted using the training data only.

## Figures

Generated figures are stored in:

`outputs/figures/`

These include exploratory visualisations, ARIMA diagnostic plots and forecasting figures.

## Environment

The project was developed using Python and Jupyter Notebook.

Main libraries include:

- pandas
- NumPy
- matplotlib
- scikit-learn
- statsmodels
- TensorFlow

Package information is provided in `requirements.txt`.

## Academic Purpose

This repository was created as part of an MSc thesis investigating weekly EUR/USD forecasting.

The project is intended for academic research and model comparison. It is not intended to provide financial or investment advice.