## Comparison: Baseline vs Improved Training (B3)

### Quantitative comparison
| Metric | Baseline CNN | Improved CNN (B3) |
|---|---:|---:|
| Train accuracy | 91.67% | 100.00% |
| Validation accuracy | 80.95% | 95.71% |
| Test accuracy | 87.14% | 94.29% |
| Best validation accuracy | 83.33% | 95.71% |
| Epochs executed | 82 | 204 |

### Discussion
- The improved training configuration (**B3**) provides a substantial increase in
  both validation and test performance with respect to the baseline CNN.
- The combination of a deeper architecture, Global Average Pooling, and controlled
  regularization significantly enhances the model’s generalization capability.
- The refinement of training dynamics through callback tuning improves convergence
  stability and allows the optimizer to reach a better final solution.
- Although the improved model reaches 100% training accuracy, its validation and
  test results remain high, indicating that the architectural and regularization
  changes were effective in limiting harmful overfitting.

### Conclusion
The improved CNN (**B3**) clearly outperforms the baseline model and is therefore
selected as the reference classifier for the subsequent experiments on:

1. model explainability through saliency maps
2. robustness under resolution degradation
3. robustness under AWGN noise
4. robustness under kernel-based blur
