# wearables-ml-examples

Reproducible ML workflows for wearable sensor time series: preprocessing & QC, 
windowing, feature engineering, modeling (classical + deep), and robust 
evaluation with clear plots. Focus on common wearable tasks like activity 
recognition and physiology/stress inference.

---

## Repository structure

```
wearables-ml-examples/
├── LICENSE 
├── README.md
├── environment.yml 
├── requirements.txt
├── notebooks/          # main analysis & modelling notebooks                                                                   
│   ├── 01_activity_recognition_from_wrist_imu_pamap2.ipynb                     
│   └── pdf/            # Notebooks PDF renders 
├── data/               # Local datasets (NOT committed)
│   └── pamap2/
└── src/                # optional Python helpers
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

- **01 – Activity Recognition from Wearable IMU (PAMAP2)**  
  [Notebook](notebooks/01_activity_recognition_pamap2.ipynb) | [PDF](notebooks/pdf/01_activity_recognition_pamap2.pdf)

  Uses the public **PAMAP2 Physical Activity Monitoring dataset** (UCI) to demonstrate a clean, wearable-style human activity recognition (HAR) workflow:
  1) load and sanity-check synchronized multi-IMU data, then subset to a watch-like wrist setup,  
  2) preprocess signals using standard vector-magnitude representations and fixed-length sliding windows,  
  3) extract simple time-domain features commonly used in wearable HAR,  
  4) train and evaluate baseline and strong classical models (Logistic Regression, HistGradientBoosting) using **subject-wise cross-validation**, and  
  5) analyze results via confusion matrices, per-subject performance variability, and PCA-based interpretability (decision regions and component loadings).

  The notebook emphasizes **sound evaluation practice, interpretability, and realistic wearable constraints**, rather than performance maximization.


---


