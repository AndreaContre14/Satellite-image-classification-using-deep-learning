# Explainability – Saliency Maps (Experiment C)

## Objective
Analyze and visualize which image regions most strongly influence the predictions
of the CNN model for satellite scene classification.

This experiment provides qualitative interpretability evidence for the final
classification model.

## Reference model
- Model: Improved CNN (Experiment B3)
- Notebook: `notebooks/saliency_C_ucmerced_B3.ipynb`

## Method
A custom function `generar_mapa_saliencia_mejorado()` was implemented with the following steps:

1. Use `tf.GradientTape()` to compute the gradient of the **predicted class score**
   with respect to the input image.
2. Aggregate gradients across channels using a **maximum reduction**, producing
   a single saliency intensity map.
3. Normalize the saliency map and apply **gamma enhancement (γ = 0.5)** to
   emphasize the most influential regions.
4. Generate the final saliency visualization as a **jet heatmap overlay**
   on the original image.

## Sampling protocol (test set)
For each class in the test dataset:
- One image is randomly selected.
- The corresponding saliency map is generated.
- The predicted class is reported.

This protocol ensures a balanced qualitative inspection across all scene categories.

## Outputs
- Original image and corresponding saliency heatmap
- Predicted label for each sample
- Visual evidence of spatial attention patterns learned by the CNN

## Figures
Selected saliency map examples are stored in:
