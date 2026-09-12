# Data availability

This directory documents the data requirements of the existing notebook.

## Required files

`SpaceX_Falcon9_Landing_Prediction.ipynb` currently references two local CSV files:

```python
data = pd.read_csv('dataset_part_2.csv')
features = pd.read_csv('dataset_part_3.csv')
```

The files are:

- `dataset_part_2.csv`
- `dataset_part_3.csv`

They are **not currently included in this repository**.

## Current expected location

Although this documentation lives under `data/`, the notebook has not been modified during the current portfolio-polish pass. Its existing `pd.read_csv(...)` calls use bare filenames, so compatible copies must currently be placed in the **repository root** for those cells to work without code changes:

```text
SpaceX_Falcon9_Landing_Prediction/
|-- dataset_part_2.csv
|-- dataset_part_3.csv
|-- SpaceX_Falcon9_Landing_Prediction.ipynb
|-- README.md
|-- requirements.txt
|-- .gitignore
`-- data/
    `-- README.md
```

## Why the CSV files are not recreated here

This polish pass is intentionally limited to documentation and repository hygiene. Reconstructing, replacing, or fabricating the datasets without a verified source could change the meaning of the notebook's analysis and stored model results.

For that reason:

- no replacement data has been generated;
- the original notebook has not been edited;
- existing stored notebook outputs have not been recalculated;
- the missing-data limitation is documented explicitly instead.

## Recommended future reproducibility pass

Once the original datasets or a verified regeneration process are available, the project can be improved by:

1. documenting the provenance and schema of each dataset;
2. deciding whether the data can be committed or must be downloaded/generated;
3. storing project data under a dedicated `data/` structure when appropriate;
4. updating notebook paths in a separate, reviewable change;
5. running the notebook from a clean environment;
6. recording reproducible model metrics and dependency versions.

Until then, the notebook should be treated as a portfolio snapshot with documented data dependencies rather than a fully reproducible pipeline.
