# Satellite Image Classification using Deep Learning

This repository presents an academic project focused on satellite scene classification
using deep learning techniques, implemented with TensorFlow and convolutional neural
networks (CNNs).

The project follows a structured experimental methodology, including baseline modeling,
training optimization, model explainability, and robustness analysis under image degradation.

## Dataset
This work uses the **UC Merced Land Use Dataset**, a widely adopted benchmark for
remote sensing scene classification (21 classes, 256 × 256 RGB images).

## Project Stages

1. **Baseline CNN model (Experiment A)**
   - Implemented and evaluated on the UC Merced dataset
   - Serves as the reference model for all comparisons
   - Notebook:
     - `notebooks/cnn_baseline_ucmerced.ipynb`

2. **Training improvements (Experiment B)**
   - Progressive architectural and training refinements (B1–B3)
   - Includes deeper architecture, regularization, and training optimization
   - Final improved model selected (**B3**)

3. **Explainability with saliency maps (Experiment C)**
   - Gradient-based saliency analysis using `tf.GradientTape`
   - Identification of relevant spatial regions influencing predictions
   - Qualitative evaluation across representative classes

4. **Robustness analysis under image degradation (Experiment D)**
   The trained model is evaluated under multiple degradation scenarios:

   - **Resolution degradation**
     - 128 × 128, 64 × 64, 32 × 32

   - **AWGN noise**
     - SNR levels: 20 dB, 10 dB, 5 dB

   - **Kernel-based blur**
     - Average kernels: 2×2, 4×4, 8×8, 16×16

   This stage analyzes how classification performance degrades under
   loss of spatial detail, noise, and blur.

## Repository Structure
- `data/`: dataset description and expected structure (dataset not included)
- `src/`: source code modules (reserved for future refactoring)
- `experiments/`: documentation of each experimental stage (A, B, C, D)
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
performance and is selected as the reference model for explainability and robustness analyses.

## Status
Advanced academic project with completed stages in:
- baseline modeling
- training optimization
- explainability analysis
- robustness evaluation under multiple degradation scenarios

Future work may include more robust architectures and transfer learning approaches.
