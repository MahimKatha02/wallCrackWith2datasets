# Wall Crack Detection Using Multiple Deep Learning Architectures (CrackSAFE-MRC)

<p align="center">
  <img src="https://img.shields.io/badge/Domain-Computer%20Vision-blue" />
  <img src="https://img.shields.io/badge/Task-Semantic%20Segmentation-green" />
  <img src="https://img.shields.io/badge/Framework-PyTorch-orange" />
  <img src="https://img.shields.io/badge/Backbone-EfficientNet--B3-yellow" />
  <img src="https://img.shields.io/badge/Architecture-U--Net%20%7C%20U--Net++%20%7C%20DeepLabV3+-purple" />
  <img src="https://img.shields.io/badge/Status-Completed-success" />
</p>

---

## Overview

Structural cracks are among the earliest indicators of infrastructure deterioration. Manual inspection is time-consuming, expensive, and prone to inconsistency. This project presents **CrackSAFE-MRC**, a deep learning-based wall crack detection and segmentation framework designed to automatically identify and localize cracks from wall surface images.

The project explores multiple state-of-the-art semantic segmentation architectures and evaluates them through extensive experimentation, threshold optimization, calibration analysis, diagnostic parity testing, explainability assessment, and reliability-aware evaluation.

The final framework combines:

- U-Net++
- EfficientNet-B3 Encoder
- Temperature Scaling Calibration
- Threshold Optimization
- Reliability Analysis
- Detection Packaging Pipeline

to produce a robust and deployment-oriented wall crack detection solution.

---

# Authors

### Mahim Chowdhury
GitHub: https://github.com/MahimKatha02

### Arafat Barman
GitHub: https://github.com/abarman079

### Project Type

**Academic Group Research Project**

---

# Project Objectives

The primary objectives of this project were:

- Detect wall cracks automatically using deep learning.
- Compare multiple semantic segmentation architectures.
- Evaluate segmentation performance using reliability-aware metrics.
- Optimize operating thresholds for real-world deployment.
- Analyze false positive and false negative behavior.
- Improve prediction confidence through calibration.
- Investigate model explainability and failure modes.
- Build a reproducible crack detection pipeline.

---

# Research Contributions

This project contributes:

✅ Multi-phase segmentation experimentation

✅ U-Net, DeepLabV3+, and U-Net++ comparison

✅ EfficientNet-B3 backbone evaluation

✅ Threshold optimization framework

✅ Temperature scaling calibration

✅ Reliability-aware evaluation

✅ Explainability analysis

✅ Failure case investigation

✅ Deployment-oriented detection packaging

---

# Dataset Information

| Property | Description |
|----------|-------------|
| Domain | Structural Health Monitoring |
| Task | Semantic Segmentation |
| Input | Wall Surface Images |
| Output | Crack Segmentation Masks |
| Problem Type | Binary Segmentation |
| Application | Infrastructure Inspection |
| Dataset Sources | Multiple Crack Datasets |
| Evaluation Type | Cross-source Reliability Analysis |

---

# Methodology

The project was conducted through multiple experimental phases.

## Data Preparation

- Dataset cleaning
- Label validation
- Image preprocessing
- Mask verification
- Dataset organization

## Model Training

Multiple architectures were trained and evaluated:

### U-Net + EfficientNet-B3

- Encoder-decoder architecture
- Strong baseline segmentation model

### DeepLabV3+ + EfficientNet-B3

- Atrous Spatial Pyramid Pooling (ASPP)
- Better contextual feature extraction

### U-Net++ + EfficientNet-B3

- Nested skip connections
- Enhanced feature fusion
- Best overall segmentation performance

---

# Experimental Phases

## Phase 1–3

### U-Net + EfficientNet-B3

Focus Areas:

- Data preprocessing
- Exploratory Data Analysis
- Model training
- Performance evaluation

---

## Phase 4

### DeepLabV3+

Focus Areas:

- Advanced semantic segmentation
- Context-aware feature extraction
- Boundary localization

---

## Phase 4B

### U-Net++

Focus Areas:

- Nested skip connections
- Feature refinement
- Performance improvement

---

## Phase 5

### Model Comparison

Comparison among:

- U-Net
- DeepLabV3+
- U-Net++

using standardized evaluation metrics.

---

## Phase 6

### Reliability Evaluation

- Performance validation
- Robustness analysis
- Error investigation

---

## Phase 7

### Diagnostic Parity Analysis

Evaluation conducted on:

- EfficientNet-B3 Eval256
- EfficientNet-B3 Eval448

to measure consistency and fairness across data distributions.

---

## Phase 8

### Threshold Tuning & Operating Point Selection

Objectives:

- Improve IoU
- Improve Dice Score
- Reduce False Positives
- Maintain Recall

---

# Workflow

```text
Wall Crack Images
        │
        ▼
Dataset Preparation
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Data Preprocessing
        │
        ▼
Model Training
        │
        ├── U-Net
        ├── DeepLabV3+
        └── U-Net++
        │
        ▼
Segmentation Prediction
        │
        ▼
Threshold Optimization
        │
        ▼
Calibration Analysis
        │
        ▼
Diagnostic Parity Evaluation
        │
        ▼
Explainability Analysis
        │
        ▼
Model Comparison
        │
        ▼
Final CrackSAFE-MRC Framework
```

---

# Repository Structure

```text
wallCrackWith2datasets/
│
├── Phase-1,2,3 (U-Net + EfficientNet-B3 encoder)
│   └── EDA
│
├── Phase-5 compare
│   ├── figures
│   └── comparison outputs
│
├── Phase-6
│
├── Phase7_Model1_Phase3R_Diagnostics_Parity
│   ├── unet_efficientnetb3_eval256
│   └── unet_efficientnetb3_eval448
│
├── Phase8_Threshold_Tuning_Operating_Point
│
├── wallcrack-phase-4-deeplabv3
│   └── deeplabv3plus_efficientnetb3_pt_files
│
└── wallcrack-phase-4B-unetpp-efficientnetb3-proto1-44
```

---

# Backbone Comparison Results

Three segmentation backbones were evaluated.

| Model | Threshold | Crack-Only IoU | Crack-Only Dice | No-Crack FP Rate |
|---------|---------:|---------:|---------:|---------:|
| U-Net + EfficientNet-B3 | 0.90 | 0.5686 | 0.7105 | 0.0183 |
| DeepLabV3+ + EfficientNet-B3 | 0.50 | 0.5728 | 0.7143 | **0.0046** |
| U-Net++ + EfficientNet-B3 | 0.50 | **0.5807** | **0.7216** | 0.0275 |

---

# Best Performing Model

## U-Net++ + EfficientNet-B3

Selected as the final backbone because it achieved:

- Highest IoU
- Highest Dice Score
- Strong generalization performance
- Superior crack localization

---

# Final CrackSAFE-MRC Performance

## Final Configuration

| Parameter | Value |
|------------|---------|
| Backbone | U-Net++ + EfficientNet-B3 |
| Calibration Temperature | 1.5565 |
| Operating Threshold | 0.55 |

---

## Final Segmentation Results

| Metric | Score |
|----------|---------:|
| Crack-Only IoU | **0.58184** |
| Crack-Only Dice | **0.72229** |
| No-Crack False Positive Rate | **0.04598** |

---

## Image-Level Classification Performance

| Metric | Score |
|----------|---------:|
| Precision | **0.9966** |
| Recall | **1.0000** |
| F1 Score | **0.9983** |
| MCC | **0.9868** |

---

## Confusion Matrix Summary

| Category | Count |
|------------|---------:|
| True Positives | 1477 |
| True Negatives | 213 |
| False Positives | 5 |
| False Negatives | 0 |

---

# Reliability & Calibration

To improve deployment readiness, temperature scaling calibration was applied.

Benefits include:

- Better confidence estimation
- Reduced overconfidence
- Improved probability calibration
- More reliable operational decisions

The final calibrated model preserved segmentation quality while improving confidence reliability.

---

# Explainability Analysis

Model explainability techniques were applied to verify decision-making behavior.

Objectives:

- Visualize model attention
- Verify crack-focused reasoning
- Detect failure patterns
- Improve interpretability

The activation maps demonstrated that the model primarily focused on crack regions instead of irrelevant background artifacts.

---

# Threshold Optimization

Extensive threshold tuning was performed to identify the optimal operating point.

### Optimization Goals

- Maximize Dice Score
- Maximize IoU
- Reduce False Positives
- Maintain High Recall

The selected threshold of **0.55** produced the most balanced performance.

---

# Domain Shift & Failure Analysis

The project investigated:

- Cross-dataset robustness
- Source-wise performance variation
- Failure mode categorization
- Environmental challenges

### Common Failure Cases

- Hairline cracks
- Low contrast surfaces
- Shadows
- Uneven lighting
- Complex wall textures

These insights guided future model improvements.

---

# Technologies Used

| Category | Tools |
|-----------|---------|
| Programming Language | Python |
| Deep Learning | PyTorch |
| Computer Vision | OpenCV |
| Data Processing | NumPy |
| Data Analysis | Pandas |
| Visualization | Matplotlib |
| Notebook Environment | Jupyter Notebook |
| Segmentation Models | U-Net, U-Net++, DeepLabV3+ |
| Backbone | EfficientNet-B3 |

---

# How to Run

## Clone Repository

```bash
git clone https://github.com/MahimKatha02/wallCrackWith2datasets.git
```

## Navigate to Project

```bash
cd wallCrackWith2datasets
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Launch Jupyter Notebook

```bash
jupyter notebook
```

## Run Experiments

Navigate to the desired phase folder and execute the notebooks.

---

# Key Findings

- U-Net++ achieved the best segmentation performance.
- DeepLabV3+ produced the lowest false positive rate.
- Calibration improved confidence reliability.
- Threshold optimization significantly improved deployment readiness.
- Explainability analysis validated model reasoning.
- Reliability-aware evaluation provided deeper insights beyond standard metrics.

---

# Future Improvements

- Vision Transformer-based segmentation
- ConvNeXt backbones
- Cross-domain evaluation
- Real-time crack detection
- Mobile deployment
- Web-based inspection dashboard
- Automated reporting system

---

# Academic Relevance

This project demonstrates the application of modern deep learning techniques to infrastructure monitoring and structural health assessment. It combines semantic segmentation, calibration, explainability, and reliability analysis into a comprehensive crack detection framework suitable for academic research and practical deployment.

---

# Acknowledgement

This work was completed as part of an academic research project focused on automated wall crack detection and structural health monitoring using deep learning-based semantic segmentation techniques.

Special thanks to all contributors, supervisors, and researchers whose work inspired and supported this project.

---

# License

This repository is intended for academic and research purposes.

Please contact the authors before commercial use.
