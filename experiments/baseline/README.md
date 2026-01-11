# Baseline CNN – UC Merced LandUse

## Objective
Establish a baseline convolutional neural network (CNN) for satellite scene classification
using the UC Merced LandUse dataset (21 classes).

## Implementation
- Framework: TensorFlow / Keras
- Dataset: UC Merced LandUse (not included in repository)
- Input size: 256 × 256 RGB
- Classes: 21
- Split strategy: 80% train / 10% validation / 10% test (stratified)

## Notebook
The full baseline pipeline is implemented in the following notebook:

- `notebooks/cnn_baseline_ucmerced.ipynb`

This notebook includes:
- Dataset loading and preprocessing
- CNN architecture definition
- Training with data augmentation
- Validation and testing
- Confusion matrix
- Per-class accuracy analysis

## Model summary
- Sequential CNN
- 3 convolutional blocks (32, 64, 128 filters)
- Batch Normalization and Dropout
- Dense classifier with Softmax output

## Training setup
- Optimizer: Adam (learning rate = 0.001)
- Loss function: Categorical Crossentropy
- Data augmentation: rotation, shifts, zoom, shear, horizontal flip
- Callbacks: EarlyStopping, ReduceLROnPlateau

## Outputs
- Training and validation accuracy/loss curves
- Confusion matrix
- Per-class accuracy

## Notes
This baseline serves as the reference point for subsequent improvements,
explainability analysis, noise robustness evaluation, and robust CNN architectures.
