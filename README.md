#  ASD prediction based on rs_fMRI brain imaging data

### Dataset

The dataset used in this project is sourced from the Autism Brain Imaging Data Exchange (ABIDE). The data has been preprocessed using Cameron Craddock's 200 ROI parcellation atlas, which includes the following key steps:

1. **Atlas and ROIs**:
   - Utilized Cameron Craddock's 200 ROI parcellation atlas.
   - Included 200 Regions of Interest (ROIs).

2. **Preprocessing Pipeline**:
   - Applied the CPAC preprocessing pipeline.
   - Implemented band-pass filtering (0.01 - 0.1 Hz) after nuisance variable regression.
   - Incorporated global mean signal correction during nuisance variable regression for strategies that included global signal correction.

### Data Overview

- **Sample Distribution**:
  - ASD (Autism Spectrum Disorder): 408 samples
  - TD (Typically Developing): 486 samples
- **Time Steps**: Ranged from 78 to 316
- **ROIs**: 200

### Data Cleaning

To ensure data quality, the following cleaning steps were applied:

- Samples with any Pearson Correlation Coefficient (PCC) value as NaN were removed.
- Post-cleaning Sample Counts:
  - ASD: 391
  - TD: 468

### Network Generation

The network features were generated as follows:

- Calculated the PCC between pairs of ROIs.
- Saved the upper diagonal of the PCC matrix (excluding the diagonal values) as the features for each subject.

### Model Development

### Model 1. Semi-supervised Autocoder classification model
### Model 2. Pre-train a VAE model followed by adding the MLP for ASD classification.
1. Train the VAE to reconstruct the input data.
2. Integrate the MLP into the Pre-trained VAE for ASD Classification.
## Results
The classification accuracy was around 66%. This suggests that further data cleaning, preprocessing, and model optimization are needed, potentially indicating some important steps or techniques were missed from the literature.
