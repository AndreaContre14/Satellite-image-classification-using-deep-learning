# Dataset

This project uses the **UC Merced Land Use Dataset**, a publicly available benchmark
dataset for remote sensing scene classification.

## Dataset reference
Yang, Y., & Newsam, S. (2010).
*Bag-of-visual-words and spatial extensions for land-use classification*.
Proceedings of the 18th SIGSPATIAL International Conference on Advances in Geographic
Information Systems (ACM GIS).
University of California, Merced.

Dataset URL:
https://www.kaggle.com/datasets/abdulhasibuddin/uc-merced-land-use-dataset

## Dataset description
- Number of classes: 21
- Images per class: 100
- Image size: 256 × 256 pixels
- Image type: RGB aerial images

## Expected directory structure

data/raw/
├─ agricultural/
├─ airplane/
├─ baseballdiamond/
├─ beach/
├─ buildings/
├─ chaparral/
├─ denseresidential/
├─ forest/
├─ freeway/
├─ golfcourse/
├─ harbor/
├─ intersection/
├─ mediumresidential/
├─ mobilehomepark/
├─ overpass/
├─ parkinglot/
├─ river/
├─ runway/
├─ sparseresidential/
├─ storagetanks/
└─ tenniscourt/

Each class directory contains 100 RGB images.

## Notes
- The dataset is **not included** in this repository due to size constraints.
- Users must download the dataset directly from the official source.
- Train/validation/test splits are generated programmatically during experimentation.
