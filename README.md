

# HiResCAM: A High-Resolution Class Activation Mapping Framework for Satellite Change Detection with XAI-Driven Interpretability

Change detection in satellite imagery is critical for monitoring urban dynamics and environmental changes. This work focuses on **mechanistic interpretability** of change detection models by integrating **explainable AI (XAI)** techniques to enhance model transparency and trustworthiness.

We utilize the **LEVIR-CD dataset**, consisting of high-resolution bi-temporal satellite image pairs, and train a **Siamese U-Net neural network** for urban change detection. To interpret the model’s predictions, we apply the **HiResCAM** method at the feature extraction layers of the network, enabling high-resolution visualization of salient regions that influenced the model’s decision-making.

![hirescam_sample_57 (1)](https://github.com/user-attachments/assets/0b9f9606-eb69-4f7c-a6b1-608f0335cbdb)

---

## 📂 Project Files

- [`HiResCAM full code.ipynb`](./HiResCAM%20full%20code.ipynb): Full training + interpretability notebook (upload directly into Kaggle)
- [`HiResCAM_model.pth`](https://drive.google.com/file/d/18fWErUWdbDNv7ndYPqFUHYiyXfpZO0am/view?usp=share_link): Pretrained model weights (download manually and upload to Kaggle notebook)
- Output image visualizations included in notebook cells

---

## 📌 Key Features

- Siamese U-Net architecture tailored for bi-temporal image change detection
- Post hoc interpretability using **HiResCAM**, providing high-resolution class activation maps
- Ability to identify which image (pre/post) the model attends to most
- Qualitative and quantitative evaluation on LEVIR-CD
- Final metrics:
  - **IoU:** 70.67%
  - **Accuracy:** 98.28%
  - **Precision:** 85.97%
  - **Recall:** 79.95%
  - **Dice Coefficient:** 82.75%

---

## 🚀 Quick Start (Kaggle Environment)

### 1. **Setup Kaggle Environment**
- Fork this repository or upload the `HiResCAM full code.ipynb` to a new [Kaggle notebook](https://www.kaggle.com/code).
- Add the **LEVIR-CD dataset** from Kaggle Datasets (`levir-cd` or your custom version).
- Upload the pretrained model downloaded from Google Drive (link above).

### 2. **Run Notebook in Order**

| Step | Section | Purpose |
|------|---------|---------|
| ✅   | Data Loading & Preprocessing | Load LEVIR-CD images and masks |
| ✅   | U-Net Siamese Class          | Define the model architecture |
| ✅   | Load Trained Model           | Load `.pth` weights |
| ✅   | HiResCAM Class               | Implement interpretability logic |
| ✅   | Visualize Outputs            | Ground truth, predictions, CAM overlays |

> 💡 We recommend using a GPU runtime (e.g., NVIDIA P100) for optimal performance.

---

## 🎯 Output: Interpretable Change Detection

Each test image pair results in:
- Pre-change & Post-change images
- Ground truth change mask
- Predicted change mask
- HiResCAM overlays for both images
- Attention gradient maps indicating key decision areas

The interpretability visualizations reveal that the model predominantly attends to the **post-change image**, raising interesting mechanistic questions for further research.

---
