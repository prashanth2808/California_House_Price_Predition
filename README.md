# California House Price Prediction (Random Forest)

A simple end-to-end **regression** project that predicts **California median house values** using the **scikit-learn California Housing dataset** and a **Random Forest Regressor**.

This repository is centered around a single Jupyter notebook:
- `house_price_rf.ipynb`

The notebook covers:
- Data loading (`fetch_california_housing`)
- Exploratory Data Analysis (EDA) and visualizations
- Train/test split
- Model training with `RandomForestRegressor`
- Evaluation using RMSE, MAE, and R²
- Feature importance visualization

---

## Dataset

The notebook uses:

- **Source:** `sklearn.datasets.fetch_california_housing(as_frame=True)`
- **Rows:** 20,640
- **Features (8 numeric):**
  - `MedInc` – median income in block group
  - `HouseAge` – median house age in block group
  - `AveRooms` – average number of rooms per household
  - `AveBedrms` – average number of bedrooms per household
  - `Population` – block group population
  - `AveOccup` – average number of household members
  - `Latitude` – block group latitude
  - `Longitude` – block group longitude
- **Target:** `MedHouseVal` (median house value, in units of $100,000)

---

## Model

- **Algorithm:** Random Forest Regression
- **Implementation:** `sklearn.ensemble.RandomForestRegressor`
- **Parameters (current notebook):**
  - `n_estimators=200`
  - `random_state=42`
  - `n_jobs=-1`

---

## Results (from the current notebook run)

On the held-out test set, the notebook reports approximately:

- **RMSE:** ~0.5040 (≈ **$50,396**)
- **MAE:** ~0.3268 (≈ **$32,681**)
- **R²:** ~0.8062

> Note: `MedHouseVal` is in $100,000 units, so the notebook multiplies errors by `100000` to show approximate USD.

---

## Visualizations

The notebook includes:

- Target distribution histogram (`MedHouseVal`)
- Correlation heatmap
- Scatter plot: `MedInc` vs `MedHouseVal`
- Geo-scatter plot (Longitude/Latitude) colored by house value
- Feature importance bar chart

---

## How to Run

### Option A: Run in Jupyter Notebook (recommended)

1. Clone the repository
2. Create and activate a virtual environment
3. Install dependencies
4. Open the notebook

Example (Windows / PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -U pip
pip install numpy pandas matplotlib seaborn scikit-learn
jupyter notebook
```

Then open:
- `house_price_rf.ipynb`

### Option B: Google Colab

Upload `house_price_rf.ipynb` to Colab and run the cells.

---

## Known Issue / Note about Feature Engineering

The notebook currently contains a feature engineering cell that references a column named `Households`:

```python
df['RoomsPerHousehold'] = df['AveRooms'] / df['Households']
df['BedroomsPerHousehold'] = df['AveBedrms'] / df['Households']
df['PopulationPerHousehold'] = df['Population'] / df['Households']
```

However, the **scikit-learn California Housing dataset does not include a `Households` column**, so this cell will raise a `KeyError` if executed.

If you want to keep ratio-based features, you can either:
- Remove this cell (the project works fine without it), or
- Switch to a dataset that includes household counts.

---

## License

If you plan to publish this on GitHub, consider adding a license (e.g., MIT License).
