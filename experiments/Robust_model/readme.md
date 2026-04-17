# Robust Model Adapted from Literature (Experiment E)

## Objective
Implement and evaluate a more advanced scene-classification model inspired by
the paper **“Deep Salient Feature Based Anti-Noise Transfer Network for Scene Classification of Remote Sensing Imagery”**.

Rather than an exact replication, this experiment represents an **adaptation**
of the main ideas that could be practically reproduced and integrated into the
current project pipeline.

The adapted model is used as an additional benchmark to compare against:

- Baseline CNN (Experiment A)
- Improved CNN (Experiment B3)

It is also evaluated under the same robustness scenarios used in previous experiments.

## Source paper
**Deep Salient Feature Based Anti-Noise Transfer Network for Scene Classification of Remote Sensing Imagery**  
Xi Gong, Zhong Xie, Yuanyuan Liu, Xuguo Shi, Zhuo Zheng  
Published: 6 March 2018

## General idea preserved from the paper
The implementation keeps the main conceptual components of the DSFATN proposal:

- extraction of deep features using **VGG19**
- use of **salient patches**
- generation of **noisy versions** of the data
- training of an **anti-noise transfer network**
- use of a **joint loss** combining classification and anti-noise regularization

These elements are consistent with the original paper, where deep salient
features are extracted and then used to train an anti-noise transfer network
with a robustness-oriented loss.

## Adaptation introduced in this project
Although the overall logic follows the paper, the implementation is not an exact reproduction.

The main adaptations are:

### 1. Saliency estimation
The original paper uses a **PBVS-based saliency strategy**.  
In this project, saliency was approximated with a practical method based on:

- grayscale conversion
- Sobel gradients
- gradient magnitude
- averaging/smoothing

Therefore, this stage is considered a **simplified operational approximation**
of the paper’s saliency mechanism rather than a strict PBVS implementation.

### 2. Patch extraction
The adapted pipeline preserves the general idea of:

- identifying salient image regions
- extracting multiple patches
- selecting patches according to saliency criteria
- resizing them to **224 × 224** for VGG19 processing

This is aligned with the spirit of the original method, although implemented
in a more practical and simplified way.

### 3. Anti-noise transfer network
The original paper proposes a compact anti-noise network with fully connected
layers and a joint loss.

In this project, this idea was implemented in **TensorFlow/Keras** using:

- **FC1** with 4096 neurons + ReLU
- **FC2** with number of output classes
- joint loss composed of:
  - cross-entropy
  - anti-noise term
  - L2 regularization

### 4. Noise perturbations
During robust training, the following perturbations were applied:

- salt-and-pepper noise
- partial occlusion
- mixed perturbation

This follows the anti-noise training spirit of the original DSFATN proposal.

### 5. Evaluation procedure
The model was evaluated using **five-fold cross-validation**, in agreement with
the evaluation logic described in the paper.

## Implementation details in this project
The adapted implementation was developed using:

- Google Colab / local execution
- UC Merced Land Use Dataset
- RGB image pipeline
- pretrained **VGG19**
- feature extraction from **fc1** (4096-dimensional vector)

Main training hyperparameters include:
- learning rate = **1e-2**
- L2 regularization = **1e-4**
- anti-noise coefficient = **1e-3**
- batch size = **32**
- number of folds = **5**
- epochs = **20** (full mode)

## Nature of this experiment
This experiment should be interpreted as:

- **an adaptation inspired by DSFATN**
- **not a strict reproduction of the original article**
- **a practical implementation of its central ideas under the constraints of this project**

## Robustness evaluation
The adapted robust model was also evaluated under the same degradation scenarios
considered in Experiment D:

### Resolution degradation
- 128 × 128
- 64 × 64
- 32 × 32

### AWGN noise
- 20 dB
- 10 dB
- 5 dB

### Kernel-based blur
- 2×2
- 4×4
- 8×8
- 16×16

This allows direct comparison between:
- the baseline CNN
- the improved CNN (B3)
- the literature-inspired robust model

under both clean and degraded conditions.

## Purpose
This experiment allows us to determine:

- whether a literature-inspired robust model provides better performance than the proposed CNNs
- how well the adapted model preserves performance under degraded input conditions
- whether the conceptual ideas of DSFATN remain effective when implemented in a simplified practical pipeline
