---
layout: page
title: Power System Fault Detection, Classification & Location
description: A machine-learning pipeline that detects, classifies, and locates faults on a 250 km three-phase transmission line, trained on MATLAB/Simulink data.
category: undergraduate
importance: 2
tech: [Machine Learning, MATLAB/Simulink]
---

<p class="project-back"><a href="{{ '/projects/' | relative_url }}">&larr; Back to Projects</a></p>

Power-system faults (short circuits) can cause severe equipment damage and outages. This project uses a machine-learning pipeline, trained on data generated from MATLAB/Simulink simulations of a three-phase transmission system, to automatically:

1. **Detect** whether a fault has occurred (binary classification).
2. **Classify** the fault among six categories (LL, LLL, LG, LLG, LLLG, and no-fault).
3. **Locate** the fault along a 250 km line.

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/power-system-fault-detection/summary_dashboard.png" alt="Summary dashboard">

## Fault detection — Random Forest

**99.54% test accuracy** (94.88% under 5-fold cross-validation) — only 11 misclassifications out of 2,401 test samples.

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/power-system-fault-detection/detection_confusion_matrix.png" alt="Detection confusion matrix">

## Fault classification — Neural Network + PCA

**80.04% test accuracy**, near-perfect on the distinct fault signatures (No-fault 100%, LL 99.5%, LG 91.2%, LLG 89.0%); the residual error comes from the naturally similar three-phase LLL / LLLG cases.

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/power-system-fault-detection/classification_confusion_matrix.png" alt="Classification confusion matrix">

## Fault location — Neural Network regressor

**RMSE 11.37 km** on a 250 km line, with an **R² of 0.974** and a mean absolute error of 5.45 km.

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/power-system-fault-detection/location_prediction.png" alt="Location prediction">

## Tech stack

MATLAB / Simulink (system model + data) · Random Forest · Neural networks (PCA + MLP) · Python (scikit-learn) for the training pipeline.
