# Results Summary

## Baseline CNN – UC Merced LandUse Dataset

### Experimental setup
- Dataset: UC Merced LandUse
- Number of classes: 21
- Image resolution: 256 × 256 RGB
- Split: 80% training, 10% validation, 10% test (stratified)
- Framework: TensorFlow / Keras
- Notebook implementation: `notebooks/cnn_baseline_ucmerced.ipynb`

### Training configuration
- Optimizer: Adam (initial learning rate = 0.001)
- Loss function: Categorical Crossentropy
- Data augmentation: rotation, translation, zoom, shear, horizontal flip
- Callbacks:
  - EarlyStopping (patience = 10)
  - ReduceLROnPlateau (factor = 0.2, patience = 5)

### Quantitative results
| Metric | Value |
|---|---:|
| Epochs executed | 82 |
| Train accuracy | 91.67% |
| Validation accuracy | 80.95% |
| Test accuracy | 87.14% |
| Best validation accuracy | 83.33% |
| Final learning rate | 1e-5 |

### Class-wise performance (selected)
- Perfect accuracy (100%): baseballdiamond, harbor, runway, sparseresidential,
  uc_airplane, uc_beach, uc_chaparral, uc_forest, uc_river
- Lower accuracy classes:
  - mobilehomepark: 60%
  - storagetanks: 50%
  - tenniscourt: 50%

### Observations
- The baseline CNN demonstrates good generalization capability.
- Lower performance in certain classes is likely caused by high inter-class visual similarity
  and limited samples per class.
- Validation accuracy shows oscillations during early epochs, which are mitigated
  through learning rate scheduling and early stopping.

### Conclusion
The baseline CNN establishes a solid performance reference for satellite scene classification.
This model will be used as a benchmark for evaluating:
1. Improved training strategies
2. Explainability methods (saliency maps)
3. Robustness under image degradation and noise
4. More robust CNN architectures
