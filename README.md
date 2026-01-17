# wearables-ml-examples

Reproducible ML workflows for wearable sensor time series: preprocessing & QC, 
windowing, feature engineering, modeling (classical + deep), and robust 
evaluation with clear plots. Focus on common wearable tasks like activity 
recognition and physiology/stress inference.

---

## Repository structure

```
wearables-ml-examples/
├─ notebooks/            # Jupyter notebooks (main deliverables)
├─ src/                  # Lightweight utilities shared across notebooks
├─ data/                 # Local datasets (NOT committed)
└─ README.md
```

---

## Software

These examples were developed with **conda 25.11.0**.

Create and activate the environment:

```
conda env create -f environment.yml
conda activate wearables-ml
jupyter lab
```

The `environment.yml` file lists the main dependencies used in the notebooks.  

For the exact snapshot of the environment used: `requirements.txt`.

```    
pip install -r requirements.txt
```

---

## Data

- Create a local `data/` directory at the repository root.
- Each notebook includes:
  - dataset download link(s)
  - expected folder/file structure under `data/`

---

## Notebooks overview

---


