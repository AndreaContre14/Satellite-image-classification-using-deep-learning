# Robustness Analysis – AWGN Noise (SNR)

## Objective
Evaluate how the CNN model behaves when the input images are corrupted with
additive white Gaussian noise (AWGN).

Noise is a common degradation in real-world remote sensing imagery due to
sensor limitations, atmospheric interference, or transmission artifacts.

## Methodology

The noise was generated using **Additive White Gaussian Noise (AWGN)** controlled
by the **Signal-to-Noise Ratio (SNR)**.

For each image:

1. The signal power was computed from the pixel intensity values.
2. The required noise power was estimated from the desired SNR level.
3. Gaussian noise with variance derived from the noise power was generated.
4. The noise was added to the original image.
5. Pixel values were clipped to the valid range [0,255].

The noisy datasets preserve the same **21-class directory structure** as the
original UC Merced dataset.

### Evaluated SNR levels

| Dataset | SNR |
|-------|-------|
| Original dataset | ∞ (no noise) |
| Noisy dataset | 20 dB |
| Noisy dataset | 10 dB |
| Noisy dataset | 5 dB |

Lower SNR values correspond to stronger noise and more severe image degradation.

## Repository notebooks

The AWGN dataset generation and experiments are implemented in the following notebooks:


notebooks/noise_dataset_generation_awgn.ipynb
notebooks/robustness_snr_20db.ipynb
notebooks/robustness_snr_10db.ipynb
notebooks/robustness_snr_5db.ipynb


## Dataset availability

The noisy datasets are not included directly in the repository due to
GitHub storage limitations.

They can be generated locally using the provided preprocessing notebook.

## Purpose of the experiment

This analysis allows us to determine:

- How sensitive the CNN model is to image noise
- How classification accuracy degrades as SNR decreases
- The minimum signal quality required to maintain reliable classification
