# Decision Trees for Car Evaluation

A machine learning classification project that predicts car acceptability classes using Decision Tree models on the Car Evaluation dataset.

## Project Overview

This repository contains a complete notebook workflow for:
- Loading and exploring the car evaluation dataset.
- Encoding categorical features.
- Training Decision Tree classifiers with both `gini` and `entropy` criteria.
- Evaluating model quality with accuracy, confusion matrix, and classification report.
- Visualizing learned trees.

## Repository Contents

- `decision-tree-car-classifier.ipynb` - Main end-to-end analysis and modeling notebook.
- `car_evaluation.csv` - Dataset used for training and evaluation.

## Dataset

The dataset includes 1,728 records and 7 columns:
- Features: `buying`, `maint`, `doors`, `persons`, `lug_boot`, `safety`
- Target: `class`

All features are categorical.

## Modeling Approach

1. Read the dataset with pandas.
2. Assign descriptive column names.
3. Split into train/test sets (`test_size=0.33`, `random_state=42`).
4. Encode categorical features using ordinal encoding (`category_encoders.OrdinalEncoder`).
5. Train two `DecisionTreeClassifier` models with `max_depth=3`:
   - Criterion `gini`
   - Criterion `entropy`
6. Compare performance using:
   - Accuracy score
   - Confusion matrix
   - Classification report

## Results

From the notebook conclusions:
- Test accuracy (gini): **0.8021**
- Test accuracy (entropy): **0.8021**
- Training accuracy: **0.7865**
- Train and test scores are close, suggesting no obvious overfitting in this setup.

## How to Run

### 1. Create and activate a virtual environment (recommended)

On Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 2. Install dependencies

```powershell
pip install jupyter numpy pandas matplotlib seaborn scikit-learn category_encoders graphviz
```

Note:
- The notebook includes fallback code to install `category_encoders` and `graphviz` if missing.
- For Graphviz rendering to work fully, you may also need the Graphviz system binary installed and available in PATH.

### 3. Launch Jupyter

```powershell
jupyter notebook
```

Then open `decision-tree-car-classifier.ipynb` and run all cells.

## Potential Improvements

- Add cross-validation for more robust performance estimates.
- Compare with ensemble methods (Random Forest, Gradient Boosting).
- Tune hyperparameters (`max_depth`, `min_samples_split`, `min_samples_leaf`).
- Add a `requirements.txt` with pinned versions for reproducibility.

## License

No license file is currently included in this repository. Add one if you want to define reuse terms explicitly.
