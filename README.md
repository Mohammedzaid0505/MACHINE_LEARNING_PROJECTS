# Flight Price Prediction

This project predicts flight ticket prices from booking and itinerary details using supervised machine learning.

## Machine Learning Project Journey

This repository documents the complete workflow for building a flight price prediction model, from data preprocessing and exploratory analysis to model evaluation and sample prediction.

### Project Updates

- **Data preprocessing:** clean the dataset, remove unsuitable columns, handle categorical features, and convert stop counts to numeric values.
- **Model training:** train Linear Regression, Decision Tree, and Random Forest regressors.
- **Evaluation:** compare model performance using regression metrics and inspect feature importance.
- **Prediction:** generate a sample flight-price prediction and save the trained Random Forest model locally.

The notebook is the working record for each stage: [flight_booking_system.ipynb](./flight_booking_system.ipynb).

## Project Contents

- `flight_booking_system.ipynb`: data cleaning, exploratory analysis, feature engineering, model training, evaluation, and example prediction.
- `Flight_Booking.csv`: flight booking dataset used by the notebook.

## Features

The notebook uses airline, source and destination cities, departure and arrival times, number of stops, travel class, flight duration, and days left before departure. The target is `price`.

## Setup

```bash
python -m venv .venv
```

Activate the environment:

```powershell
.venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Open `flight_booking_system.ipynb` in VS Code or Jupyter and run the cells from top to bottom. The notebook reads `Flight_Booking.csv` from the repository root, so it is portable across machines.

## Workflow

1. Load and inspect the data.
2. Remove export and high-cardinality columns, then check missing values, duplicates, and outliers.
3. Encode categorical features and convert stop counts to numeric values.
4. Split and standardize the data.
5. Compare linear regression, random forest, and decision tree regressors using regression metrics.
6. Inspect feature importance and generate a sample price prediction.

## Results and Insights

The notebook compares three regression models:

| Model | R-squared |
| --- | ---: |
| Linear Regression | 0.9099 |
| Decision Tree | 0.9755 |
| Random Forest | 0.9848 |

Random Forest achieved the best reported performance with an $R^2$ score of `0.9848`. The trained model is saved as `random_forest_regressor_model.pkl` when the relevant notebook cell is run.

## Dataset

The included CSV contains flight booking records. The original dataset reference in the notebook is available [here](https://drive.google.com/file/d/1DbdetuzKL0ULawxgKtBtWrRWtfv52MhA/view?usp=sharing).

## Reproducibility

The train/test split uses `random_state=42`. Generated `.pkl` model files are ignored by Git because they are local artifacts and can be recreated by running the notebook.