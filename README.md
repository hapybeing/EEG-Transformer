# EEG-Transformer: Topographical Decoding of Spatial Visual Stimuli

An independent research project focused on treating raw, high-dimensional EEG time-series as sequential tokens for self-attention mechanisms. Developed and executed entirely via a tablet-first cloud workflow.

## Overview
This repository contains the architecture and proof-of-concept training loop for the **EEG-Transformer**. Unlike traditional BCI pipelines that rely on destructive spatial filtering (ICA/CSP), this model ingests raw 60-channel topographical tensors directly into a 4-layer Transformer encoder.

## Technical Specifications
- **Architecture:** 4-Layer Transformer Encoder
- **Attention Heads:** 4
- **Latent Dimension ($d_{model}$):** 128
- **Input:** Raw EEG Epochs (60 channels × 500ms window)
- **Optimizer:** AdamW ($lr=1e-3$, weight decay=$1e-4$)
- **Objective:** Binary Cross-Entropy (BCE) for spatial visual field classification

## Empirical Results (Baseline)
The current iteration was trained on the standardized **MNE-Sample dataset** ($N=144$ trials). 
- **Convergence:** The model achieved architectural stability with a plateaued Binary Cross-Entropy loss of **0.692**.
- **Analysis:** This loss aligns with the theoretical maximum entropy of binary classification ($-\ln(0.5) \approx 0.693$), indicating that while the architecture is structurally sound, the sample size is currently the primary bottleneck for semantic discriminative learning.

## Deployment Profile
This project was developed under a constrained, mobile-first research paradigm:
- **Environment:** Google Colaboratory (Cloud GPU)
- **Hardware:** $1 \times$ NVIDIA Tesla T4
- **Workflow:** Xiaomi Pad 6 / Tablet-first orchestration

## Research Paper
The full technical report, including the mathematical formulation of the InfoNCE scaling roadmap, is available on **Zenodo**:
[INSERT YOUR ZENODO DOI LINK HERE]

## License
MIT
