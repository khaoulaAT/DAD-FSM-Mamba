# DAD-FSM-Mamba

## Video Anomaly Detection in Drone Videos Based on Mamba Architecture

This repository presents **DAD-FSM-Mamba**, a deep learning architecture for **Video Anomaly Detection (VAD)** in drone videos.

The proposed approach extends the original **DAD-FSM (Drone Anomaly Detection via Future Segmentation Modeling)** framework by integrating **Mamba-based State Space Models (SSMs)** to improve spatio-temporal modeling while reducing computational complexity from **O(n²)** to **O(n)**.

This work was developed as a Master's Final Project in **Artificial Intelligence and Digital Computing (AIDC)** at the **Faculty of Sciences and Techniques of Béni Mellal**, Sultan Moulay Slimane University.

---

## Project Overview

Video anomaly detection aims to automatically identify abnormal events in drone video sequences.

Unlike traditional surveillance videos, aerial videos present several challenges:

* Camera motion
* Perspective variations
* Scale changes
* Dynamic backgrounds
* Long-range temporal dependencies

To address these limitations, DAD-FSM-Mamba combines:

* Spatial feature extraction
* Temporal modeling using Mamba
* Multimodal fusion using State Space Models
* Future segmentation prediction
* Motion-aware learning

---

## Proposed Architecture

The architecture is composed of four main modules:

### 1. Spatial Feature Extractor

* ResNet-50 backbone
* Spatial Attention Block
* Feature projection layer

### 2. DroneVideoMamba

* Temporal sequence modeling
* Long-range dependency learning
* Linear complexity O(n)

### 3. MambaCrossSSM

* Multimodal fusion mechanism
* RGB and segmentation interaction
* Selective State Space Modeling

### 4. Decoder

* Future segmentation prediction
* Reconstruction of target segmentation maps

---

## Dataset

### UIT-ADrone Dataset

The experiments are conducted on the UIT-ADrone benchmark dataset.

Characteristics:

* Drone aerial videos
* Urban anomaly scenarios
* One-Class Learning protocol
* Normal videos used during training
* Normal and anomalous videos used during testing

### Preprocessing

* Frame extraction
* Resize to 224 × 224
* Temporal sequences of T = 4 frames
* Motion mask generation using Canny edge detection
* Data augmentation

---

## Training Configuration

| Parameter       | Value           |
| --------------- | --------------- |
| Resolution      | 224 × 224       |
| Sequence Length | 4               |
| Batch Size      | 8               |
| Learning Rate   | 3e-4            |
| Epochs          | 15              |
| Optimizer       | AdamW           |
| Platform        | Kaggle          |
| GPU             | Tesla P100 16GB |

---

## Evaluation Metrics

The following metrics are used:

* AUC (Area Under Curve)
* EER (Equal Error Rate)
* ROC Curve
* Training Loss

---

## Results

### Quantitative Results

| Metric          | Value   |
| --------------- | ------- |
| AUC             | 71.31 % |
| EER             | 35.97 % |
| Best Loss       | 0.43290 |
| Test Samples    | 43,141  |
| Training Epochs | 15      |

### Comparison with DAD-FSM

| Metric     | DAD-FSM | DAD-FSM-Mamba |
| ---------- | ------- | ------------- |
| AUC        | 68.13 % | 71.31 %       |
| Complexity | O(n²)   | O(n)          |
| Epochs     | 30      | 15            |

The proposed architecture improves anomaly detection performance while significantly reducing computational complexity.

---

## Notebook Content

The notebook includes:

* Dataset preparation and preprocessing
* Motion mask generation using Canny edge detection
* DAD-FSM-Mamba implementation
* Model training
* Quantitative evaluation (AUC, EER, ROC)
* Qualitative analysis
* Comparison with the original DAD-FSM architecture

---

## Technologies

* Python
* PyTorch
* NumPy
* OpenCV
* Matplotlib
* Scikit-Learn
* Kaggle Notebooks

---

## Author

**Khaoula Ait Idder**

Master of Science and Technology

Artificial Intelligence & Digital Computing (AIDC)

Faculty of Sciences and Techniques of Béni Mellal

Sultan Moulay Slimane University

Academic Year: 2025–2026

Supervisor: **Pr. Youssef Saadi**
