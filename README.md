# Alignment-Aware Cross-Modal Swin for Multisensor Information Fusion:Application to Hyperspectral–LiDAR Land-Cover Mapping

# Summary
ACMS features a parallel-stream design using separable convolution tokenization and modality-specific Swin backbones to capture hierarchical spatial-spectral features. These features are integrated via a gated cross-modality dual-attention fusion module and a shared transformer head for precise LULC classification.

<img width="1252" height="465" alt="architecture" src="https://github.com/user-attachments/assets/30e6dc3d-afe5-4189-95f4-467eb9f0edcd" />

![GAT-Transformer Architecture](architecture.jpg)

- [X] **Hybrid Architecture**: Synergistically combines Separable Convolution Tokenization to capture multi-scale local textures with Dual-Stream Swin -Transformers to model hierarchical spatial-spectral and structural dependencies.
- [X] **Alignment-Aware Fusion**: Introduces a novel Gated Cross-Modality Dual-Attention mechanism that employs learnable modality weighting and gating to maintain robustness against spatial misalignment and sensor noise.
- [X] **Multi-Benchmark Validation**: Proven state-of-the-art performance on the classification of complex landscapes using Houston 2013 (92.51% OA), Trento (99.93% OA), and MUUFL (92.56% OA) datasets.
- [X] **Unified Co-Learning**: Systematically addresses the five core challenges of multimodal learning—Representation, Translation, Alignment, Fusion, and Co-learning—within a single end-to-end framework.
- [X] **Adaptive Integration**: Features a Shared Transformer Head that refines fused feature vectors to ensure bidirectional information exchange and highly discriminative joint representations.

