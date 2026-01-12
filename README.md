# Satellite Image Classification using Deep Learning

This repository presents an academic project focused on satellite scene classification
using deep learning techniques, implemented with TensorFlow and convolutional neural
networks (CNNs).

The project follows a structured experimental methodology, including baseline modeling,
training optimization, and model explainability analysis.

## Dataset
This work uses the **UC Merced Land Use Dataset**, a widely adopted benchmark for
remote sensing scene classification (21 classes, 256 × 256 RGB images).

## Project Stages

1. **Baseline CNN model**
   - Implemented and evaluated on the UC Merced dataset
   - Reference notebook:
     - `notebooks/cnn_baseline_ucmerced.ipynb`

2. **Training improvements (Experiment B)**
   - Progressive architectural and training refinements (B1–B3)
   - Final improved model selected (B3)

3. **Explainability with saliency maps (Experiment C)**
   - Gradient-based saliency analysis using `tf.GradientTape`
   - Qualitative inspection of spatial attention across classes

4. **Noise robustness analysis** *(planned)*
   - Evaluation under image degradation and noise conditions

## Repository Structure
- `data/`: dataset description and expected structure (dataset not included)
- `src/`: source code modules (reserved for future refactoring)
- `experiments/`: documentation of each experimental stage (A, B, C)
- `docs/`: methodology and consolidated results summaries
- `notebooks/`: executable notebooks for all experiments

## Framework
- TensorFlow / Keras

## Results overview

| Model | Validation Accuracy | Test Accuracy |
|---|---:|---:|
| Baseline CNN | 80.95% | 87.14% |
| Improved CNN (B3) | **95.71%** | **94.29%** |

The improved training strategy (Experiment B3) significantly enhances generalization
performance and is selected as the final classification model for subsequent analyses.

## Status
Advanced academic project with completed baseline, training optimization, and
explainability stages.
