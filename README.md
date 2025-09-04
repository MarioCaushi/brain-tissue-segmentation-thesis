# Brain Tissue Segmentation Using Different AI Architectures

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.14-orange?logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-2.14-red?logo=keras&logoColor=white)
![Medical Imaging](https://img.shields.io/badge/Domain-Medical%20Imaging-lightblue)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN%2FUNet-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-ISBR18-yellow)
![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)
![Status](https://img.shields.io/badge/Status-Completed-success)

This repository contains the final report for my undergraduate thesis titled  
**"Brain Tissue Segmentation Using Different AI Architectures"**,  
submitted in partial fulfillment of the requirements for the B.Sc. in Computer Engineering at Epoka University.

---

## Thesis Overview

This study explores and compares a range of artificial intelligence (AI) methods for brain tissue segmentation on 3D MRI volumes.  
The segmentation targets **gray matter (GM)**, **white matter (WM)**, and **cerebrospinal fluid (CSF)** using the **IBSR18 dataset**.  
The work aims to evaluate performance across both traditional and deep learning approaches, with a focus on segmentation quality, model architecture, and computational trade-offs.

---

## Implemented Methods

The following models were developed and evaluated:

- **K-Means** – Unsupervised hard clustering baseline  
- **Fuzzy C-Means (FCM)** – Soft clustering for probabilistic membership modeling  
- **3D CNN** – Minimal volumetric convolutional baseline  
- **3D U-Net** – Encoder–decoder architecture with skip connections  
- **DenseUNet** – U-Net enhanced with dense blocks and attention gates  
- **Hybrid DenseUNet–U-Net** – Custom model combining dense encoders with U-Net decoding  

---

## Dataset

- **Name:** IBSR18 (Internet Brain Segmentation Repository)  
- **Format:** T1-weighted 3D MRI scans (`.nii`)  
- **Preprocessing Steps:**
  - Skull stripping  
  - Bias field correction  
  - Image registration  
  - Intensity normalization  
  - Contrast enhancement (CLAHE)  

📌 **Dataset Access:** [IBSR Repository on Neuroimaging Informatics Tools and Resources](https://www.nitrc.org/projects/ibsr)

---

## Experimentation Environment

All experiments were conducted using **Google Colab Pro**, utilizing **NVIDIA T4 and A100 GPUs**.  
The following techniques were used to maximize training efficiency:
- Mixed precision training  
- Patch-based input volumes (e.g., `128³`)  
- Early stopping and learning rate scheduling  
- AdamW optimizer with weight decay  

---

## Report Contents

The thesis report includes:

- Structured literature review with state-of-the-art comparison  
- Detailed methodology for each segmentation model  
- Overview of experimental design and training configurations  
- Evaluation using Dice Similarity Coefficient (DSC)  
- Visual segmentation outputs (axial, sagittal, coronal)  
- Tables and diagrams illustrating architectures and per-class performance  

---

## Results

The table below shows the segmentation performance using the Dice Similarity Coefficient (DSC) for the best configuration of each model:

| Model       | Avg DSC  | CSF    | GM    | WM    |
|-------------|---------|-------|-------|-------|
| K-Means      | 0.5880  | 0.0000 | 0.8820 | 0.8830 |
| FCM          | 0.5910  | 0.0010 | 0.8910 | 0.8820 |
| CNN          | 0.3720  | 0.0000 | 0.5720 | 0.5420 |
| U-Net        | 0.7508  | 0.5280 | 0.8807 | 0.8435 |
| DenseUNet    | 0.6387  | 0.2632 | 0.8291 | 0.8238 |

---

## File Included

- `MC_Thesis.pdf`: Complete thesis report (text, methodology, results, diagrams, discussion)

---

## Future Work

This thesis can be extended with the following ideas:

- **Transformer-based Models:** Implement Vision Transformers (ViTs) or hybrid CNN–Transformer architectures for volumetric segmentation.
- **Post-Processing Refinement:** Use Conditional Random Fields (CRFs) or morphological operations to enhance segmentation boundaries.
- **Larger & Multimodal Datasets:** Apply the models to bigger, diverse datasets for better generalization.
- **3D Instance Segmentation:** Explore anatomical structure–level segmentation for finer granularity.

---

## Citation

If referring to this work, please cite as:

> **Caushi, M.** (2025). *Brain Tissue Segmentation Using Different AI Architectures.*  
> Bachelor Thesis, Department of Computer Engineering, Epoka University.

---

## License

This repository is licensed under the  
**Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)**.  

See the [LICENSE](LICENSE) file for full terms.  
You may use, adapt, and share the contents **for non-commercial academic purposes only** with proper attribution.

---

## Notes

- The IBSR18 dataset is **not included** in this repository due to licensing restrictions.  
- A link to the official dataset source is provided for reproducibility.
