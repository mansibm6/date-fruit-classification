# Date fruit classification

Filters date-fruit measurements and compares KNN, SVM, logistic regression, random forest, gradient boosting, decision tree, and hard voting.

## Setup and execution

Use Python 3.11 and a separate virtual environment for this project. Run commands from this folder:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python check_inputs.py
python -m jupyterlab
```

On Windows, activate with `.venv\Scripts\activate`. For notebooks, select this environment’s kernel and execute from the top in a fresh kernel. The first code cell exposes `INPUT_PATHS` where old machine-specific paths existed. `PROJECT_DATA_DIR` changes the base for those configured paths; remaining relative paths use the notebook working directory.

## Notebooks

- [date-classification-let-s-vote-acc-95.ipynb](date-classification-let-s-vote-acc-95.ipynb)

## Inputs

Supply these inputs yourself; no dataset is downloaded automatically:

- `Date_Fruit_Datasets.xlsx`

## Outputs

Exploratory plots, model comparisons, and confusion matrices.

## Implementation and limitations

The workbook requires Class plus the original measurement columns (including AREA, PERIMETER, SOLIDITY, and MAJOR_AXIS). Scaling is now fitted on training rows only. Gradient boosting predictions use the selected model. Parameter sweeps still examine the test split in this historical exploratory workflow; add nested validation before treating scores as final estimates.

## Verification

The workspace regression suite checks source/notebook validity and selected behavior with bundled or synthetic inputs. Full experiment training and historical metric reproduction are not implied. See the workspace `REFACTOR_REPORT.md` for exact test coverage and unresolved runtime requirements.
