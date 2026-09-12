# SpaceX Falcon 9 Landing Prediction

A Jupyter Notebook data science project focused on analyzing SpaceX Falcon 9 launch data and experimenting with classification models for first-stage landing prediction.

The notebook brings together exploratory analysis, SQL-backed data work, geospatial visualization, an interactive Dash dashboard, feature preprocessing, traditional machine-learning classifiers, and a TensorFlow/Keras neural-network experiment.

> **Reproducibility note**
>
> The notebook references `dataset_part_2.csv` and `dataset_part_3.csv`, but those files are **not currently included in this repository**. Cells that depend on them cannot be reproduced from a fresh clone until compatible copies of those datasets are supplied. See [`data/README.md`](data/README.md) for the current file expectations.

## Project goals

This project explores a binary classification workflow around Falcon 9 landing outcomes. Its main technical goals are to:

- inspect and visualize launch-related data;
- work with tabular data using Pandas and NumPy;
- query locally stored data through SQLite/SQLAlchemy and IPython SQL tooling;
- build geospatial visualizations with Folium;
- create interactive visual analysis with Dash and Plotly;
- preprocess features for supervised learning;
- train and compare multiple classification algorithms;
- evaluate predictions with classification reports and confusion matrices;
- experiment with a small neural network using TensorFlow/Keras.

## Workflow represented in the notebook

```text
Prepared CSV datasets
        |
        v
Tabular exploration and visualization
        |
        +--> SQLite / SQL analysis
        |
        +--> Folium geospatial maps
        |
        +--> Dash / Plotly dashboard
        |
        v
Feature preparation and scaling
        |
        v
Train / test split
        |
        +--> Logistic Regression
        +--> Support Vector Machine (SVM)
        +--> Decision Tree
        +--> K-Nearest Neighbors (KNN)
        +--> TensorFlow / Keras experiment
        |
        v
Classification reports and confusion matrices
```

## Models used

The notebook contains training and evaluation code for the following scikit-learn classifiers:

| Model | Notebook usage |
| --- | --- |
| Logistic Regression | Training, prediction, classification report, confusion matrix |
| Support Vector Machine (`SVC`) | Training, prediction, classification report, confusion matrix |
| Decision Tree | Training, prediction and evaluation |
| K-Nearest Neighbors | Training, prediction and evaluation |

It also includes a TensorFlow/Keras `Sequential` model using dense layers as an additional experiment.

The stored notebook output includes model-evaluation results from previous runs. These should be treated as **exploratory notebook results rather than a reproducible benchmark** until the missing datasets and a fully pinned environment are restored.

## Technology stack

| Area | Tools used in the notebook |
| --- | --- |
| Language / notebook | Python, Jupyter Notebook |
| Data manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Interactive analytics | Dash, Plotly |
| Geospatial analysis | Folium |
| SQL / persistence | SQLite, SQLAlchemy, IPython SQL |
| Machine learning | scikit-learn |
| Neural-network experiment | TensorFlow, Keras |

## Repository structure

```text
SpaceX_Falcon9_Landing_Prediction/
|-- SpaceX_Falcon9_Landing_Prediction.ipynb  # Original analysis notebook
|-- README.md                                 # Project documentation
|-- requirements.txt                          # Notebook dependencies
|-- .gitignore                                # Local/generated files excluded from Git
`-- data/
    `-- README.md                              # Dataset availability and expected paths
```

## Data availability

The current notebook loads the following local files directly:

```python
data = pd.read_csv('dataset_part_2.csv')
features = pd.read_csv('dataset_part_3.csv')
```

Those CSV files are not present in the repository at this time.

Because the notebook currently references the filenames without a directory prefix, the least invasive way to reproduce its existing behavior is to place compatible copies in the **repository root**:

```text
SpaceX_Falcon9_Landing_Prediction/
|-- dataset_part_2.csv
|-- dataset_part_3.csv
|-- SpaceX_Falcon9_Landing_Prediction.ipynb
`-- ...
```

The notebook has intentionally **not** been changed during this documentation-polish pass. A future reproducibility pass can move datasets into `data/` and update the notebook paths in a controlled change.

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/SC-Sergio/SpaceX_Falcon9_Landing_Prediction.git
cd SpaceX_Falcon9_Landing_Prediction
```

### 2. Create a virtual environment

**Windows (PowerShell):**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**Linux / macOS:**

```bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Supply the required datasets

Before running all notebook cells, provide compatible versions of:

- `dataset_part_2.csv`
- `dataset_part_3.csv`

Place them in the repository root unless the notebook paths are deliberately updated. More details are documented in [`data/README.md`](data/README.md).

### 5. Open the notebook

```bash
jupyter notebook SpaceX_Falcon9_Landing_Prediction.ipynb
```

## Current reproducibility limitations

This repository is currently best viewed as a documented portfolio snapshot of the analysis rather than a fully reproducible package.

The main limitations are:

1. `dataset_part_2.csv` and `dataset_part_3.csv` are missing from the repository.
2. The notebook contains package-installation cells and reflects the environment in which it was originally executed.
3. Dependency versions were not originally captured in a project-level lockfile.
4. The analysis is organized as a single notebook rather than a modular Python package or pipeline.
5. Existing model metrics come from stored notebook executions and should not be interpreted as a stable production benchmark.

## Suggested next improvements

A future technical-polish pass could:

- restore or reproducibly regenerate the two required datasets;
- move project data into a dedicated `data/` structure and update notebook paths;
- pin a tested dependency set;
- remove environment-specific installation cells from the analysis flow;
- refactor reusable preprocessing and model-evaluation logic into Python modules;
- add automated checks or CI for a clean notebook execution;
- document model comparison results only after reproducing them from a clean environment.

## Scope of this repository

The purpose of this repository is to demonstrate an applied data-science workflow using Falcon 9 landing prediction as the problem domain. It is an exploratory/educational project and is not an official SpaceX project or production prediction service.
