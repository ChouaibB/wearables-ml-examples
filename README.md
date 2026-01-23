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
├── notebooks/                                                  # main analysis & modelling notebooks
│   ├── 01_activity_recognition_from_wrist_imu_pamap2.ipynb
│   ├── 02_hr_estimation_from_wrist_ppg_acc_ppgdalia.ipynb                     
│   └── pdf/                                                    # Notebooks PDF renders 
├── data/                                                       # Local datasets (NOT committed)
│   ├── pamap2/
│   └── PPGDalia/
└── src/                                                        # optional Python helpers
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

- **01 – Activity Recognition from Wrist IMU (PAMAP2)** [Notebook](notebooks/01_activity_recognition_from_wrist_imu_pamap2.ipynb) | [PDF](notebooks/pdf/01_activity_recognition_from_wrist_imu_pamap2.pdf)

  Uses the public **PAMAP2 Physical Activity Monitoring dataset** (UCI) to demonstrate a clean, wearable-style human activity recognition (HAR) workflow:
  1) load and sanity-check synchronized multi-IMU data, then subset to a watch-like wrist setup,  
  2) preprocess signals using standard vector-magnitude representations and fixed-length sliding windows,  
  3) extract simple time-domain features commonly used in wearable HAR,  
  4) train and evaluate baseline and strong classical models (Logistic Regression, HistGradientBoosting) using **subject-wise cross-validation**, and  
  5) analyze results via confusion matrices, per-subject performance variability, and PCA-based interpretability (decision regions and component loadings).

  The notebook emphasizes **sound evaluation practice, interpretability, and realistic wearable constraints**, rather than performance maximization.

- **02 – Heart Rate Estimation from Wrist PPG + Accelerometer (PPG-DaLiA)** [Notebook](notebooks/02_hr_estimation_from_wrist_ppg_acc_ppgdalia.ipynb) | [PDF](notebooks/pdf/02_hr_estimation_from_wrist_ppg_acc_ppgdalia.pdf)

  Uses the **PPG-DaLiA dataset** (Zenodo benchmark format) to demonstrate a compact, wearable-focused regression workflow for **heart rate estimation under motion**:
  1) load and inspect pre-segmented wrist **PPG + accelerometer** windows with ECG-derived HR ground truth,  
  2) design a small set of **interpretable, reliability-aware features** capturing motion intensity and PPG periodicity,  
  3) train and compare classical regression models (Ridge, SVR, HistGradientBoosting) on a fixed train/test split,  
  4) evaluate performance using **MAE, RMSE, and tolerance-based accuracy** (within ±5/±10 bpm), and  
  5) analyze errors through **motion-aware diagnostics**, including error vs motion intensity, error distributions, and parity plots.

  The notebook emphasizes **model-level motion artefact compensation, robust evaluation, and interpretability**, providing a strong classical baseline before more complex end-to-end deep wearable models.

---


