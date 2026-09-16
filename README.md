```markdown
# GCMS: Gated Cross-Modal Swin Transformer for Hyperspectral–LiDAR Classification

## Summary

GCMS is a gated cross-modal Swin Transformer designed for multimodal hyperspectral image (HSI) and LiDAR classification. The framework employs modality-specific Swin Transformer encoders to extract hierarchical spatial-spectral and structural representations from HSI and LiDAR data. These modality-specific features are integrated through reciprocal cross-modal attention, learnable directional weighting, and token- and feature-dependent gating, followed by shared contextual refinement for discriminative land-cover classification.

<img width="2145" height="698" alt="GCMS architecture" src="https://github.com/user-attachments/assets/205d9a72-8d09-40b8-902c-5570e6c010e4" />

### Key Features

- [X] **Dual-Stream Swin Architecture**: Uses modality-specific Swin Transformer encoders to model hierarchical spatial-spectral information from HSI and complementary structural information from LiDAR.

- [X] **Bidirectional Cross-Modal Attention**: Employs reciprocal cross-modal attention to enable information exchange between HSI and LiDAR representations in both directions.

- [X] **Learnable Directional Weighting**: Introduces learnable weighting of the two cross-modal attention directions to adaptively combine complementary information from HSI-to-LiDAR and LiDAR-to-HSI interactions.

- [X] **Token- and Feature-Dependent Gating**: Applies a gating mechanism to adaptively modulate the fused cross-modal representation according to token- and feature-level information.

- [X] **Multi-Benchmark Evaluation**: Evaluated on three widely used HSI–LiDAR benchmark datasets: Houston 2013, Trento, and MUUFL.

- [X] **Parameter-Efficient Design**: The proposed GCMS model contains 0.334M trainable parameters while providing competitive classification performance across the evaluated benchmarks.

## Installation & Environment Setup

The main software environment uses **Python 3.10+**.

The complete list of required packages is provided in the repository. Key dependencies include:

### Deep Learning
- `torch` (PyTorch)
- `torchvision`
- `timm`

### Remote Sensing & Scientific Computing
- `spectral`
- `scipy`

### Data Processing
- `numpy`
- `pandas`
- `scikit-learn`

### Visualization
- `matplotlib`
- `seaborn`
- `tqdm`

## Datasets

### Houston 2013

The Houston 2013 dataset integrates hyperspectral and LiDAR observations over an area of 349 × 1905 pixels. The HSI data contain 144 spectral bands, while the LiDAR data provide complementary elevation information.

### Trento

The Trento dataset provides co-registered HSI and LiDAR observations over a region of 166 × 600 pixels. The HSI data contain 64 spectral bands, while the LiDAR data contain two channels providing complementary structural information.

### MUUFL

The MUUFL dataset provides HSI and LiDAR observations over a region of 325 × 220 pixels. The HSI data contain 64 spectral bands, while the LiDAR data contain two channels providing complementary structural information.

## Models

The repository includes implementations or references to several conventional and deep-learning-based methods used for comparison.

### Conventional Classifiers

- [RF](https://ieeexplore.ieee.org/document/1396322)
- [SVM](https://ieeexplore.ieee.org/document/1323134)

### CNN-Based Methods

- [Coupled CNN](https://ieeexplore.ieee.org/abstract/document/8985546/)
- [CCR-NET](https://ieeexplore.ieee.org/abstract/document/9598903)

### Transformer-Based Methods

- [SpectralFormer](https://ieeexplore.ieee.org/abstract/document/9627165)
- [EXViT](https://ieeexplore.ieee.org/abstract/document/10147258)

## Results

GCMS is evaluated on the Houston 2013, Trento, and MUUFL datasets using overall accuracy (OA), average accuracy (AA), and the kappa coefficient ($\kappa$).

| Dataset | OA (%) |
|---------|--------:|
| Houston 2013 | 92.51 |
| Trento | 99.93 |
| MUUFL | 92.18 |

For complete experimental results, ablation studies, and implementation details, please refer to the manuscript and the accompanying materials.

## Code and Supporting Materials

The implementation of GCMS is publicly available in this repository.

The supporting data and materials used in the experiments are also provided through the project resources.

## How to Cite

This work has been submitted to **Neurocomputing**. If you use this code or the associated materials in your research, please cite the following work once it is published:

> Ouerhani, B., Rhif, M., & Ben Abbes, A.  
> GCMS: Gated Cross-Modal Swin Transformer for Hyperspectral–LiDAR Classification.  
> *Neurocomputing*, under review.

## License

Please refer to the repository license for the terms governing the use and distribution of this code.
```
