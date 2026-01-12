# Satellite Image Classification using Deep Learning

This repository contains a deep learning–based approach for satellite image classification
using TensorFlow and convolutional neural networks (CNNs).

## Project Stages
1. Baseline CNN model: The baseline CNN model is fully implemented and documented in the following notebook:

- `notebooks/cnn_baseline_ucmerced.ipynb`

This notebook serves as the reference point for all subsequent experiments.
2. Training improvements
3. Explainability with saliency maps
4. Noise robustness analysis
5. Robust CNN architecture (ongoing)

## Repository Structure
- `data/`: dataset structure and splits (images not included)
- `src/`: source code
- `experiments/`: documentation of each experimental stage
- `docs/`: methodology and results summaries

## Framework
- TensorFlow / Keras

## Status
Ongoing academic project.

## Results overview

| Model | Validation Accuracy | Test Accuracy |
|---|---:|---:|
| Baseline CNN | 80.95% | 87.14% |
| Improved CNN (B3) | **95.71%** | **94.29%** |

The improved training strategy (Experiment B3) significantly enhances generalization
and serves as the final classification model for further analyses.

