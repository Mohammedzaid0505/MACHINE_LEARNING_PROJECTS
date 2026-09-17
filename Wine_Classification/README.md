# Wine Classification with SVC

This project classifies the scikit-learn Wine dataset with a Support Vector Classifier (SVC). It also uses StandardScaler and PCA to create a two-dimensional visualization of the decision boundary.

## Project contents

- `Wine_Classification.ipynb`: data preparation, model training, evaluation, and artifact export.
- `outputs/wine_svc_model.pkl`: serialized model bundle created with `joblib`.
- `outputs/confusion_matrix.png`: test-set confusion matrix.
- `outputs/pca_decision_boundary.png`: PCA decision-boundary visualization.
- `requirements.txt`: Python dependencies.

## Run locally

1. Create and activate a virtual environment.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Open `Wine_Classification.ipynb` in Jupyter or VS Code and run all cells.

The notebook uses the built-in scikit-learn Wine dataset, so no external dataset download is required. Running it recreates the files in `outputs/`.

## Model artifact

The pickle file contains a dictionary with:

- `classifier`: the SVC trained on the original 13 features.
- `scaler` and `pca`: the preprocessing objects used for the visualization workflow.
- `pca_classifier`: the linear SVC trained on the two PCA components.
- `feature_names` and `target_names`: dataset metadata.

Load it with:

```python
import joblib

model_bundle = joblib.load("outputs/wine_svc_model.pkl")
predictions = model_bundle["classifier"].predict(new_samples)
```