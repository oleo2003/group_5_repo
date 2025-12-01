# Paper Reproduction Log - Engineer 2: Martina Riascos

# Biologist 2's papers

Paper 1 – Targeting Neurodegeneration: three machine learning methods for G9a inhibitors discovery Using PubChem and scikit-learn

- **Link to paper**: [https://doi.org/10.1007/s10822-025-00642-z](https://doi.org/10.1007/s10822-025-00642-z)
- **Code repo**: [https://github.com/articlesmli/G9a_Inhibitors_efficacy](https://github.com/articlesmli/G9a_Inhibitors_efficacy)

---

**What we tried**

- Cloned the GitHub repository
- Opened the README and found no runnable scripts or notebooks; only links to raw PubChem assays and preprocessed datasets on HuggingFace.
- Created a Conda environment:
  ```
  conda create -n g9a python=3.10 -y
  conda activate g9a
  conda install -c conda-forge rdkit -y
  pip install datasets numpy pandas scikit-learn xgboost matplotlib
  ```
- Loaded the referenced dataset from HuggingFace:
    `ivanovaml/G9a_onlyInhibitors_targetEfficacy_basic`
- Wrote a custom Python pipeline (`run_replication.py`) since no official code was provided:

  * Loaded dataset as pandas dataframe (71,193 rows, 65 columns of molecular descriptors).
  * Selected numeric features only.
  * Used **Efficacy** as the regression target.
  * Split data 80/20 into training and testing sets.
  * Trained a **GradientBoostingRegressor** model (paper’s primary model).
  * Evaluated using MAE, RMSE, and R².

---

### What went wrong

  - Script expected label column named `targetEfficacy`, dataset column actually named `Efficacy`. Caused a pandas `KeyError`, fixed by updating the target variable name.

  - Metric calculation using `mean_squared_error(..., squared=False)` failed because the installed sklearn version did not support the `squared` argument., Fixed by computing RMSE manually using:
    ```
    sqrt(mean_squared_error())
    ```
---

### Final execution

- Successfully ran:
  ```
  python run_replication.py
  ```
- Model: GradientBoostingRegressor
- Dataset: 71,193 molecules, numeric molecular descriptors only
- Train/test split: 80% / 20%

**Results:**

* MAE: **29.37**
* RMSE: **36.09**
* R²: **0.14**

---

### Conclusion

Successfully ran a custom ML pipeline using the provided HuggingFace dataset.

Trained a GradientBoostingRegressor and obtained evaluation metrics (MAE = 29.37, RMSE = 36.09, R² = 0.14).

Results did not match the paper’s reported performance (MAE ≈ 21.48%).

Full reproduction not possible due to missing details on feature engineering, hyperparameters, and cross-validation not included in the repository.