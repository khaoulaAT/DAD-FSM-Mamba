# DAD-FSM-Mamba

## Video Anomaly Detection in Drone Videos Based on Mamba Architecture

This repository presents **DAD-FSM-Mamba**, a deep learning architecture for **Video Anomaly Detection (VAD)** in drone videos.

The proposed approach extends the original **DAD-FSM (Drone Anomaly Detection via Future Segmentation Modeling)** framework by replacing attention-based temporal modeling with **Mamba-based State Space Models (SSMs)**, enabling efficient long-range dependency learning with **linear complexity O(n)** instead of **quadratic complexity O(n²)**.

This work was developed as a Master's Final Project entitled:

**"Video Anomaly Detection in Drone Videos Based on Mamba Architecture"**

within the Master's program **Artificial Intelligence and Digital Computing (AIDC)** at the Faculty of Sciences and Techniques of Béni Mellal, Sultan Moulay Slimane University.

---

## Project Overview

Video anomaly detection aims to automatically identify abnormal events in video sequences.

Compared to traditional surveillance videos, drone videos are particularly challenging due to:

- Camera motion
- Perspective changes
- Scale variations
- Dynamic backgrounds
- Long-range temporal dependencies

To address these challenges, DAD-FSM-Mamba combines:

- Spatial feature extraction
- Mamba-based temporal modeling
- State Space multimodal fusion
- Future segmentation prediction
- Motion-aware learning

---

## Proposed Architecture

The proposed architecture consists of four main modules:

### 1. Spatial Feature Extraction

- ResNet-50 backbone pretrained on ImageNet
- Frozen feature extractor
- Spatial Attention Block
- Feature projection to latent embedding space

### 2. DroneVideoMamba

- Temporal sequence modeling
- Bidirectional State Space Modeling
- Long-range dependency learning
- Linear complexity O(n)

### 3. MambaCrossSSM

- Multimodal fusion mechanism
- RGB and segmentation feature interaction
- Cross-modal State Space Modeling

### 4. Segmentation Decoder

- Temporal feature aggregation
- Future segmentation prediction
- Reconstruction of target segmentation maps

---

## Dataset

### UIT-ADrone Dataset

Experiments are conducted on the UIT-ADrone benchmark dataset.

Characteristics:

- Drone aerial videos
- Urban anomaly scenarios
- One-Class Learning protocol
- Normal samples used for training
- Normal and anomalous samples used for evaluation

### Data Preprocessing

- Frame extraction
- Resize to 224 × 224
- Temporal sequences of T = 4 frames
- Motion-mask generation using Canny edge detection
- Data augmentation

### Dataset Statistics

| Split | Samples |
|---------|---------:|
| Training | 39,163 |
| Testing | 43,141 |

---

## Training Configuration

| Parameter | Value |
|------------|------------|
| Resolution | 224 × 224 |
| Sequence Length | 4 |
| Batch Size | 8 |
| Effective Batch Size | 16 |
| Learning Rate | 3e-4 |
| Boosted Learning Rate | 3e-3 |
| Epochs | 20 |
| Optimizer | AdamW |
| Loss Function | MAFL |
| Platform | Kaggle |
| GPU | Tesla P100 16GB |

---

## Model Statistics

| Component | Parameters |
|------------|------------:|
| Total Parameters | 85,570,645 |
| Trainable Parameters | 38,554,581 |
| Frozen Parameters | 47,016,064 |

---

## Evaluation Metrics

The following metrics are used:

- AUC (Area Under the ROC Curve)
- EER (Equal Error Rate)
- ROC Curve
- MAFL Training Loss

---

## Final Results

### Quantitative Results

| Metric | Value |
|----------|----------:|
| AUC | **71.97 %** |
| EER | **35.35 %** |
| Best Loss | **0.43111** |
| Test Samples | **43,141** |
| Training Epochs | **20** |

---

## Comparison with DAD-FSM

| Metric | DAD-FSM | DAD-FSM-Mamba |
|----------|----------:|----------:|
| AUC | 68.13 % | **71.97 %** |
| Temporal Complexity | O(n²) | **O(n)** |
| Training Epochs | 30 | **20** |

The proposed DAD-FSM-Mamba architecture improves anomaly detection performance while significantly reducing temporal complexity.

---

## Notebook Content

The notebook includes:

- Dataset preparation and preprocessing
- Motion-mask generation using Canny edge detection
- Spatial Attention implementation
- DroneVideoMamba implementation
- MambaCrossSSM implementation
- MAFL Loss implementation
- Model training
- Checkpoint management
- Quantitative evaluation (AUC, EER, ROC)
- Qualitative visualization
- DAD-FSM vs DAD-FSM-Mamba comparison

---

## Qualitative Analysis

The notebook provides qualitative visualizations including:

- RGB input frames
- Ground-truth segmentation maps
- Predicted segmentation maps
- Normal scene examples
- Anomalous scene examples
- Representative samples from the test set

---

## Technologies

- Python
- PyTorch
- NumPy
- OpenCV
- Matplotlib
- Scikit-Learn
- Kaggle Notebooks

---

## Repository Structure

```text
DAD-FSM-Mamba/
│
├── README.md
├── DAD_FSM_Mamba_UIT_ADrone.ipynb
└── checkpoints/
```

---

## Author

**Khaoula Ait Idder**

Master Artificial Intelligence and Digital Computing (AIDC)

Faculty of Sciences and Techniques of Béni Mellal

Sultan Moulay Slimane University

Academic Year: 2025–2026

Supervisor: **Pr. Youssef Saadi**
