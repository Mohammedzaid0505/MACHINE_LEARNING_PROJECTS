# Flight Price Prediction

This project predicts flight ticket prices from booking and itinerary details using supervised machine learning.

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

## Dataset

The included CSV contains flight booking records. The original dataset reference in the notebook is available [here](https://drive.google.com/file/d/1DbdetuzKL0ULawxgKtBtWrRWtfv52MhA/view?usp=sharing).

## Reproducibility

The train/test split uses `random_state=42`. Generated `.pkl` model files are ignored by Git because they are local artifacts and can be recreated by running the notebook.