# Improved Training – Experiment B (UC Merced LandUse)

## Objective
Improve the baseline CNN by iteratively modifying architecture and training strategy.

## Baseline reference
- `notebooks/cnn_baseline_ucmerced.ipynb`

## Experiment notebooks
- B1: `notebooks/cnn_B1_architecture.ipynb`
- B2: `notebooks/cnn_B2_regularization.ipynb`
- B3: `notebooks/cnn_B3_callbacks.ipynb`

---

## B1 – Architecture enhancement
- Filters increased: 32/64/128 → 64/128/256
- L2 regularization (Conv + Dense)
- Global Average Pooling instead of Flatten
- Max epochs: 500 with EarlyStopping

## B2 – Regularization tuning
- L2: Conv λ=0.0005, Dense λ=0.001
- Dropout: 0.2 (Conv), 0.3 (Dense)
- Adam optimizer (lr=1e-3)
- EarlyStopping (patience=15)
- ReduceLROnPlateau (patience=7)

## B3 – Callback refinement (final)
- No architecture changes
- EarlyStopping patience: 25
- ReduceLROnPlateau patience: 12

## Status
B3 is selected as the final improved training configuration.
Quantitative results will be reported after evaluation.
