# 🌌 Hybrid CatBoost-Based Few-Shot Learning (Cat-FSL) Model for Inter-Class Classification in Hyperspectral Images

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![PyTorch](https://img.shields.io/badge/Framework-PyTorch-red.svg)
![CatBoost](https://img.shields.io/badge/Model-CatBoost-orange.svg)
![GPU](https://img.shields.io/badge/GPU-CUDA%20Enabled-green.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

---

## 📘 Overview

**Cat-FSL** is a **hybrid CatBoost-based Few-Shot Learning (FSL)** framework designed to enhance **inter-class classification** in **Hyperspectral Images (HSI)** when labeled data is scarce.  
The model combines **CatBoost-derived global probabilistic features** with **CNN-based local spectral embeddings** in a **dual-path architecture**, optimized via a **Prototypical Network**.  
This fusion enables **robust prototype learning**, **improved inter-class separability**, and **enhanced generalization** across complex HSI datasets.

---

## 🧠 Key Contributions

- **Dual-Path Hybrid Architecture**:  
  Integrates CatBoost global probabilistic features with CNN-based spectral embeddings for balanced global-local feature learning.  

- **Optimal Distortion Search (ODS)**:  
  Introduces adaptive augmentation (Gaussian noise, Mixup, jittering) to enhance prototype consistency and spectral robustness.  

- **Prototypical Network Optimization**:  
  Learns discriminative embeddings and prototypes under a 5-way 5-shot episodic training strategy.  

- **Comprehensive Sensitivity Analysis**:  
  Evaluates the effect of CatBoost hyperparameters, learning rate, and iteration count on Accuracy, Kappa, and ARI metrics.  

- **Spatial–Spectral Interpretability**:  
  Employs **Lacunarity Analysis** to measure spatial heterogeneity and feature diversity across scales.

---

## 🧩 Methodology

| Component | Description |
|------------|-------------|
| **CatBoost Path** | Generates class-level probabilistic feature vectors (1000 iterations, depth=6, lr=0.1). |
| **CNN Path** | Extracts multi-scale spectral features using 1D convolutions (kernel sizes 9, 7, 5). |
| **Fusion & ProtoNet** | Combines global and local features; learns prototypes in a discriminative metric space. |
| **Episodic Training** | 5-way 5-shot configuration, 500 episodes, with cosine annealing and AdamW optimizer. |
| **ODS** | Filters augmented samples based on Prototype Separation Ratio (PSR > 1.2× baseline). |

---

## 🛰️ Datasets Used

- **Indian Pines (AVIRIS)** — 145×145 pixels, 200 spectral bands, 16 classes.  
- **Salinas (AVIRIS)** — 512×217 pixels, 204 spectral bands, 16 classes.  
- Both datasets preprocessed for class balance and normalized spectral bands.

---

## 📊 Experimental Results

| Dataset | Model | OA (%) | Kappa | ARI | Avg Inter-Class Distance |
|----------|--------|--------|--------|------|----------------------------|
| Indian Pines | Cat-FSL | **98.92** | **0.96** | **0.92** | **186.53** |
| Salinas | Cat-FSL | **98.19** | **0.94** | **0.90** | **136.80** |

- Outperforms models such as **MAML (71.04%)**, **CRSSNet (78.03%)**, and **SPN (94.35%)**.  
- Produces **tight prototype clusters** with clear separation (validated by **UMAP** & **t-SNE**).  
- Demonstrates **high lacunarity**, confirming spatial heterogeneity preservation.

---

## 🌈 Lacunarity Analysis

Lacunarity quantifies **texture variation** and **spatial complexity** in hyperspectral features.  
Cat-FSL achieves maximum lacunarity across multiple scales, indicating its ability to maintain multiscale spatial heterogeneity and robust feature diversity.

| Dataset | Box Size | Cat-FSL Lacunarity |
|----------|-----------|--------------------|
| Indian Pines | 8 | **803,828.50** |
| Salinas | 8 | **23,142,940.00** |

---

## 🧾 Ablation Study

| Variant | Dataset | OA (%) | Kappa | ARI | Avg Dist |
|----------|----------|---------|--------|------|-----------|
| CatBoost Only | Indian Pines | 81.62 | 0.73 | 0.61 | 0.83 |
| CNN Only (Base-FSL) | Indian Pines | 84.00 | 0.80 | 0.70 | 14.06 |
| **Cat-FSL (Full)** | Indian Pines | **96.90** | **0.96** | **0.92** | **51.61** |

---

## 📈 Visual Results

- **Confidence Visualizations:** UMAP & t-SNE show clear cluster separation.  
- **Feature Attribution:** CatBoost importance and CNN Integrated Gradients reveal key spectral bands.  
- **Inter-class Maps:** Cat-FSL delivers sharper, less ambiguous land-cover boundaries than XGBoost or AdaBoost.  

---

## 🧪 Sensitivity Analysis

| Hyperparameter | Observation |
|----------------|--------------|
| CatBoost Iterations ↑ | Improved Accuracy, Kappa, ARI |
| Learning Rate (0.05–0.1) | Balanced generalization & prototype consistency |
| ODS Threshold (1.2× PSR) | Optimal trade-off between diversity and robustness |

---

## 🧬 Comparison with State-of-the-Art

| Model | OA (Indian Pines) | OA (Salinas) |
|--------|-------------------|--------------|
| CRSSNet | 78.03 | 96.20 |
| TFSL | 98.10 | 99.05 |
| SPN | 94.35 | — |
| **Cat-FSL (Ours)** | **98.92** | **98.19** |

Cat-FSL achieves higher inter-class separation and clustering consistency than competing FSL and hybrid architectures.

---

## 🏁 Conclusion

Cat-FSL integrates CNN-based spectral embeddings with CatBoost probabilistic priors in a dual-path few-shot framework.  
It enhances **prototype consistency**, **class separability**, and **spatial interpretability** under limited supervision.  
Validated on **Indian Pines** and **Salinas**, Cat-FSL achieves **state-of-the-art results** in hyperspectral classification with robust generalization and interpretability.

---

## 🧑‍💻 Author

**Ushneesh Chattopadhyay**  
Department of Computer Science and Engineering  
Institute of Engineering and Management (IEM), Kolkata, India  

📧 [ushneesh2003chattopadhyay@gmail.com](mailto:ushneesh2003chattopadhyay@gmail.com)

---

## License
This project is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).
Usage and redistribution permitted with proper citation.

---

## 📚 Citation

If you use this repository or model in your research, please cite:

> Chattopadhyay, U., Das Bhattacharjee, A., Chakravarty, D.  
> *“Hybrid CatBoost-Based Few-Shot Learning Model for Inter-Class Classification in Hyperspectral Images.”*  
