# Wall Crack Detection Using Multiple Deep Learning Architectures

<p align="center">
  <img src="https://img.shields.io/badge/Project-Wall%20Crack%20Detection-brightgreen" />
  <img src="https://img.shields.io/badge/Domain-Computer%20Vision-blue" />
  <img src="https://img.shields.io/badge/Task-Crack%20Segmentation-purple" />
  <img src="https://img.shields.io/badge/Language-Python-orange" />
  <img src="https://img.shields.io/badge/Framework-PyTorch-yellow" />
</p>

## Overview

**Wall Crack Detection Using Multiple Deep Learning Architectures** is a computer vision project focused on automated crack detection and segmentation from wall surface images. The project evaluates multiple state-of-the-art semantic segmentation architectures and diagnostic approaches across several experimental phases.

The repository contains exploratory data analysis, segmentation experiments, model comparison studies, threshold tuning experiments, diagnostic parity evaluations, result visualizations, and trained model outputs.

---

## Authors

**Mahim Chowdhury**
GitHub: https://github.com/MahimKatha02

**Mohammad Akibul Hasan Arman (Group Member/ Collaborator)**
GitHub: https://github.com/abarman079

### Project Type

Academic Group Project

---

## Project Goals

* Detect wall cracks automatically using deep learning.
* Compare multiple segmentation architectures.
* Evaluate segmentation quality across different datasets.
* Analyze threshold tuning strategies.
* Perform diagnostic parity evaluation.
* Compare model performance using standard segmentation metrics.
* Build a reproducible workflow for crack detection research.

---

## Dataset Information

| Item         | Details                                      |
| ------------ | -------------------------------------------- |
| Dataset Type | Wall crack image dataset                     |
| Domain       | Civil Engineering, Infrastructure Monitoring |
| Task         | Semantic Segmentation                        |
| Input        | Wall surface images                          |
| Output       | Crack masks                                  |
| Objective    | Accurate crack localization and segmentation |

---

## Methods Used

The project investigates several deep learning architectures for crack detection.

### Segmentation Models

| Model                   |
| ----------------------- |
| U-Net                   |
| U-Net++                 |
| DeepLabV3               |
| DeepLabV3+              |
| EfficientNet-B3 Encoder |

---

## Experimental Phases

### Phase 1–3

U-Net with EfficientNet-B3 encoder

Includes:

* Dataset preparation
* Data preprocessing
* Model training
* Evaluation
* Exploratory Data Analysis (EDA)

### Phase 4

DeepLabV3 / DeepLabV3+

Focus:

* Semantic segmentation
* Feature extraction
* Crack boundary localization

### Phase 4B

U-Net++ with EfficientNet-B3

Focus:

* Improved feature fusion
* Enhanced segmentation performance

### Phase 5

Model Comparison

Comparison of:

* U-Net
* U-Net++
* DeepLabV3+

Includes performance visualizations and comparative analysis.

### Phase 6

Advanced evaluation and experimental refinement.

### Phase 7

Diagnostic Parity Analysis

Experiments conducted on:

* EfficientNet-B3 evaluation set 256
* EfficientNet-B3 evaluation set 448

### Phase 8

Threshold Tuning Operating Point Analysis

Focus:

* Precision-recall tradeoff
* Threshold optimization
* Operating point selection

---

## Workflow

```text
Wall Crack Dataset
        │
        ▼
Data Preparation
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Model Training
        │
        ├── U-Net
        ├── U-Net++
        ├── DeepLabV3
        └── DeepLabV3+
        │
        ▼
Segmentation Prediction
        │
        ▼
Threshold Optimization
        │
        ▼
Diagnostic Parity Analysis
        │
        ▼
Model Comparison
        │
        ▼
Final Evaluation
```

---

## Repository Structure

```text
wallCrackWith2datasets/
│
├── Phase-1,2,3 (U-Net + EfficientNet-B3 encoder)/
│   └── EDA/
│
├── Phase-5 compare/
│   ├── figures/
│   └── comparison outputs
│
├── Phase-6/
│
├── Phase7_Model1_Phase3R_Diagnostics_Parity/
│   ├── unet_efficientnetb3_eval256/
│   └── unet_efficientnetb3_eval448/
│
├── Phase8_Threshold_Tuning_Operating_Point/
│
├── wallcrack-phase-4-deeplabv3/
│   └── deeplabv3plus_efficientnetb3_pt_files/
│
└── wallcrack-phase-4B-unetpp-efficientnetb3-proto1-44/
```

---

## Technologies Used

| Category             | Tools / Libraries          |
| -------------------- | -------------------------- |
| Programming Language | Python                     |
| Deep Learning        | PyTorch                    |
| Data Processing      | NumPy, Pandas              |
| Visualization        | Matplotlib                 |
| Computer Vision      | OpenCV                     |
| Notebook Environment | Jupyter Notebook           |
| Segmentation Models  | U-Net, U-Net++, DeepLabV3+ |
| Encoder Backbone     | EfficientNet-B3            |

---

## Evaluation Metrics

The models were evaluated using:

| Metric                        |
| ----------------------------- |
| Accuracy                      |
| Precision                     |
| Recall                        |
| F1 Score                      |
| IoU (Intersection over Union) |
| Dice Coefficient              |
| Confusion Matrix              |

---

## How to Run This Project

### 1. Clone Repository

```bash
git clone https://github.com/MahimKatha02/wallCrackWith2datasets.git
```

### 2. Navigate to Project

```bash
cd wallCrackWith2datasets
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Run Experiments

Navigate to the relevant phase folder and execute the notebooks.

---

## Project Outputs

| Output             | Description                |
| ------------------ | -------------------------- |
| Segmentation Masks | Crack prediction outputs   |
| Evaluation Reports | Performance metrics        |
| Comparison Figures | Model comparison plots     |
| Threshold Analysis | Operating point evaluation |
| Diagnostic Results | Parity assessment reports  |

---

## Key Contributions

* Multi-phase crack segmentation pipeline.
* Comparative analysis of segmentation architectures.
* DeepLabV3+ implementation for crack localization.
* U-Net++ experiments with EfficientNet-B3.
* Threshold tuning and operating point optimization.
* Diagnostic parity evaluation framework.

---

## Future Improvements

* Add Vision Transformer based segmentation.
* Experiment with ConvNeXt backbones.
* Add cross-dataset validation.
* Improve crack boundary refinement.
* Deploy as a web application.
* Add experiment tracking using MLflow or Weights & Biases.

---

## Academic Relevance

This project demonstrates the application of deep learning and semantic segmentation techniques to infrastructure monitoring and structural health assessment. It explores multiple architectures and evaluation strategies for automated wall crack detection.

---

## Acknowledgement

This work was completed as an academic group project focused on wall crack segmentation and analysis using modern deep learning techniques.

---

## License

No license has been added yet. Add an appropriate open-source license before public distribution.
