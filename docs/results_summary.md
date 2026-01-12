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
- The improved training configuration (B3) yields a **substantial gain** in validation
  and test performance compared to the baseline CNN.
- Architectural enhancements (deeper network, Global Average Pooling) combined with
  controlled regularization significantly improve generalization.
- Training dynamics refinement (callback patience) stabilizes convergence and enables
  higher final performance.
- The performance gap between training and validation remains controlled, indicating
  limited overfitting.

### Conclusion
The improved CNN (B3) clearly outperforms the baseline and is selected as the
reference model for subsequent explainability (saliency maps) and robustness analyses.
