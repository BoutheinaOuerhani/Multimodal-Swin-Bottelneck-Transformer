# GCMS: Gated Cross-Modal Swin Transformer with Bidirectional Attention for Hyperspectral–LiDAR Classification
 
Official implementation of **GCMS**, a compact multimodal Transformer for HSI–LiDAR land-use/land-cover (LULC) classification. GCMS combines modality-specific Swin-style encoders, bidirectional cross-modal attention, learnable directional weighting, and a data-dependent gate to adaptively fuse hyperspectral and LiDAR representations.
 
> **GCMS: Gated Cross-Modal Swin Transformer with Bidirectional Attention for Hyperspectral–LiDAR Classification**
> Boutheina Ouerhani, Manel Rhif, Ali Ben Abbes
> University of Manouba, Tunisia
 
![GCMS Architecture](./gcms-architecture.png)
## Highlights
 
- **Modality-specific Swin encoders**: separable-convolution tokenization + 4 stacked Swin-style window-attention blocks with bottleneck refinement, learned independently for HSI and LiDAR.
- **Gated bidirectional cross-modal fusion**: reciprocal cross-attention (H←L and L←H) combined via global learnable directional coefficients and a token/feature-wise sigmoid gate.
- **Residual fusion + shared Transformer encoder** refine the fused multimodal tokens before attention-pooling classification.
- **Extremely compact**: only **0.334M** trainable parameters — fewer than ExViT, SpectralFormer, and MSFMamba, comparable to MFT.
- **Robustness analysis**: tolerant to small horizontal HSI–LiDAR misregistration and mild HSI Poisson noise (without retraining).
## Results
 
| Dataset      | OA (%) | AA (%) | Kappa (%) |
|--------------|:------:|:------:|:---------:|
| Houston2013  | 92.51  | 93.41  | 91.87     |
| Trento       | 99.93  | 99.89  | 99.91     |
| MUUFL        | 92.18  | 92.97  | 89.68     |
 

 
## Repository Structure
 
```
Multimodal-Swin-Bottelneck-Transformer/
│
├── model/
│ └── model.ipynb
├── gcms-architecture.png
├── .gitignore
├── LICENSE
└── README.md
```
## Compared Models

| Model | Main approach |
|---|---|
| **CCR-Net** | Coupled CNN-based multimodal fusion |
| **Coupled CNN** | Coupled CNN branches for HSI and LiDAR |
| **ExViT** | Extended Vision Transformer for multimodal fusion |
| **MFT** | Multimodal Fusion Transformer |
| **MSFMamba** | Multi-scale Mamba-based feature extraction and fusion |
| **SpectralFormer** | Transformer-based hyperspectral feature learning |
| **GCMS (Ours)** | Swin Transformer + bidirectional cross-modal attention + gated fusion |

## Datasets
 
GCMS is evaluated on three public HSI–LiDAR benchmarks:
 
| Dataset      | Scene size    | HSI bands | LiDAR bands | Classes | Patch size |
|--------------|---------------|:---------:|:-----------:|:-------:|:----------:|
| Houston2013  | 349 × 1905    | 144       | 1           | 15      | 14 × 14    |
| Trento       | 166 × 600     | 64        | 2           | 6       | 9 × 9      |
| MUUFL        | 325 × 220     | 64        | 2           | 11      | 11 × 11    |
 
Download links:

- **Houston2013** — [IEEE GRSS Data Fusion Contest 2013](http://www.grss-ieee.org/community/technical-committees/data-fusion/2013-ieee-grss-data-fusion-contest/)
- **Trento** — [Trento Dataset](https://github.com/tyust-dayu/Trento)
- **MUUFL** — [GatorSense/MUUFLGulfport](https://github.com/GatorSense/MUUFLGulfport)
 
## Installation
 
```bash
git clone https://github.com/<your-username>/GCMS.git
cd GCMS
pip install -r requirements.txt
```
 
 
## Usage
 
**Training**
```bash
python train.py --config configs/houston2013.yaml
```

**Evaluation**
```bash
python eval.py --config configs/houston2013.yaml --checkpoint checkpoints/gcms_houston2013.pth
```
 
**Pixel-wise inference / land-cover map**
```bash
python inference.py --config configs/houston2013.yaml --checkpoint checkpoints/gcms_houston2013.pth --output maps/houston2013_pred.png
```
 
## Key Hyperparameters
 
| Parameter | Value |
|---|---|
| Embedding dimension $D$ | 16 |
| Attention heads $h$ | 8 |
| Swin window size $M$ | 7 |
| Bottleneck reduction $r$ | 4 |
| Shared encoder layers $L_s$ | 2 |
| Feed-forward dim $D_{ff}$ | 64 |
| Batch size | 64 |
| Epochs | 1000 (Houston2013) / 500 (MUUFL) / 200 (Trento) |

