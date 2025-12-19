# Alignment-Aware Cross-Modal Swin for Multisensor Information Fusion:Application to Hyperspectral–LiDAR Land-Cover Mapping

# Summary
ACMS features a parallel-stream design using separable convolution tokenization and modality-specific Swin backbones to capture hierarchical spatial-spectral features. These features are integrated via a gated cross-modality dual-attention fusion module and a shared transformer head for precise LULC classification.

<img width="1252" height="465" alt="architecture" src="https://github.com/user-attachments/assets/30e6dc3d-afe5-4189-95f4-467eb9f0edcd" />

- [X] **Hybrid Architecture**: Synergistically combines Separable Convolution Tokenization to capture multi-scale local textures with Dual-Stream Swin -Transformers to model hierarchical spatial-spectral and structural dependencies.
- [X] **Alignment-Aware Fusion**: Introduces a novel Gated Cross-Modality Dual-Attention mechanism that employs learnable modality weighting and gating to maintain robustness against spatial misalignment and sensor noise.
- [X] **Multi-Benchmark Validation**: Proven state-of-the-art performance on the classification of complex landscapes using Houston 2013 (92.51% OA), Trento (99.93% OA), and MUUFL (92.56% OA) datasets.
- [X] **Unified Co-Learning**: Systematically addresses the five core challenges of multimodal learning Representation, Translation, Alignment, Fusion, and Co-learning—within a single end-to-end framework.
- [X] **Adaptive Integration**: Features a Shared Transformer Head that refines fused feature vectors to ensure bidirectional information exchange and highly discriminative joint representations.

## Installation & Environment Setup
The main software used was **Python 3.10+**.
The complete list of required packages is listed here, key dependencies include:
* **Deep Learning:** `torch`(PyTorch) , `torchvision`, `timm`
* **Remote Sensing:** `spectral`, `scipy`
* **Data Processing:** `numpy`, `pandas`, `scikit-learn`
* **Visualization:** `matplotlib`, `seaborn`, `tqdm`

## Datasets
- [X] **Houston 2013 Dataset:** The Houston2013 dataset integrates HSI and LiDAR data, covering an area of 349 × 1905 pixels. The HSI component contains 144 spectral bands, providing rich detail for material and surface discrimination, while the LiDAR modality consists of a single elevation band, offering complementary structural information. 
- [X] **Trento Dataset:** The Trento dataset provides HSI and LiDAR observations over a region of 166 × 600 pixels. The HSI data comprise 64 spectral bands, while the LiDAR modality includes two bands that capture elevation and intensity information.
- [X] **MUUFL Dataset:** The MUUFL dataset provides HSI and LiDAR observations over a region of 325 × 220 pixels. The HSI data contain 64 spectral bands, while the LiDAR modality includes two bands capturing elevation and intensity information.

## Models
The following conventional classifier methods will be available:
* [RF](https://ieeexplore.ieee.org/document/1396322) 
* [SVM](https://ieeexplore.ieee.org/document/1323134)
  
The following classic backbone networks methods will be available:
* [Coupled CNN](https://ieeexplore.ieee.org/abstract/document/8985546/)
* [CCR-NET](https://ieeexplore.ieee.org/abstract/document/9598903/)
  
The following classic backbone networks methods will be available:
* [SpectralFormer](https://ieeexplore.ieee.org/abstract/document/9627165)
* [EXViT](https://ieeexplore.ieee.org/abstract/document/10147258/)
## How to cite?
This manuscript has been submitted to **Information Fusion**. If you use this code or data, please cite it as follows once published:
> Ouerhani, B., Ben Abbes, A., & Rhif, M.(Under Review). Alignment-Aware Cross-Modal Swin for Multisensor Information Fusion:Application to Hyperspectral–LiDAR Land-Cover Mapping, *Information Fusion*.
