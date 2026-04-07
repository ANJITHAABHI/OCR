# OCR
SROIE-OCR-Forensic: A Deep Learning-based Optical Character Recognition (OCR) system utilizing a CRNN (CNN + BiLSTM + CTC) architecture to extract and structure text from scanned receipts. Designed for automated data auditing and financial document digitization.
---

# CRNN-based OCR for Receipt Information Extraction (SROIE)

This repository contains a Deep Learning-based Optical Character Recognition (OCR) system optimized for the **SROIE (Scanned Receipts OCR and Information Extraction)** dataset. The project implements a **Convolutional Recurrent Neural Network (CRNN)** to transform unstructured receipt images into structured, machine-readable CSV data for financial auditing and forensic analysis.

## 📌 Project Overview
The objective of this project is to bridge the gap between physical document scanning and digital data analytics. By combining computer vision (CNN) with sequence modeling (LSTM), the system accurately recognizes text in complex, real-world receipt layouts.

### Key Features
* **Hybrid CRNN Architecture**: Integrates ResNet-style convolutional layers with Bidirectional LSTMs.
* **CTC Loss Integration**: Employs Connectionist Temporal Classification for alignment-free sequence learning.
* **Forensic Auditing Tool**: Includes a post-processing script to filter keywords (e.g., "TOTAL", "TAX") and export structured reports.
* **High Accuracy**: Achieved a **Character Error Rate (CER) of 4.03%** on the SROIE benchmark.

## ⚙️ Methodology
The system follows a modular pipeline:
1.  **Preprocessing**: Images are converted to grayscale and normalized to a $32 \times 128$ resolution.
2.  **Feature Extraction**: A CNN backbone extracts spatial features from the receipt images.
3.  **Sequence Labeling**: A BiLSTM layer processes the spatial features to understand character context and linguistic patterns.
4.  **Transcription**: A CTC decoder converts the model's probabilistic outputs into the final text string.



## 🛠️ Implementation Stack
* **Language**: Python 3.x
* **Deep Learning Framework**: PyTorch
* **Image Processing**: OpenCV, PIL (Pillow)
* **Data Handling**: Pandas, NumPy
* **Metrics**: Edit-Distance (for CER calculation)

## 📂 Repository Structure
```text
├── TA2_PROJECT_OCR.ipynb          # Full training and evaluation pipeline
├── AI_TA2_Presentation_OCR    # Project presentation slides
├── requirements.txt
└── README.md                  # Project documentation


```

Installation
To set up the environment, ensure you have Python 3.8+ installed, then run:

Bash
pip install -r requirements.txt
Note: If you are using a GPU (like the RTX 4060), ensure your CUDA version matches your PyTorch installation.

Dataset Access
The model is trained and evaluated on the SROIE (Scanned Receipts OCR and Information Extraction) dataset. You can download the official data from the following sources:

Kaggle (Pre-organized): SROIE Dataset on Kaggle: https://www.kaggle.com/datasets/urbikn/sroie-datasetv2

## 📊 Results
The model demonstrates robust performance on structured financial documents:
* **Total Words Recognized**: 5000+ (Sample evaluation)
* **Character Error Rate (CER)**: 0.0403
* **Hardware Used**: Optimized for NVIDIA RTX 4060 GPU (CUDA enabled).

## ⚠️ Limitations & Future Scope
* **Limitations**: Performance may decrease with extreme image blur or non-standard fonts.
* **Future Scope**: Implementing Transformer-based architectures (e.g., Donut or TrOCR) and expanding support for multilingual receipts.

## 👥 Contributors
* **Adithiyan R S** - Lead Developer & Model Architecture
* **Miracle Elliot Tettevi** - Data Engineering & Preprocessing
* **Anjitha B** - Documentation & Presentation Lead

---
*Developed as part of the AI TA2 Project, April 2026.*
