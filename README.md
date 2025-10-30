# 🧠 Cat-FSL: Hybrid CatBoost-Based Few-Shot Learning for Hyperspectral Image Classification

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-red.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

**Cat-FSL** is a hybrid **CatBoost-based Few-Shot Learning (FSL)** framework designed to improve **inter-class classification** in **Hyperspectral Images (HSI)** under limited labeled data conditions. The model employs a **dual-path architecture** that integrates **CatBoost-derived global probabilistic features** with **CNN-based local spectral embeddings**, enabling robust prototype learning and enhanced class separability.

In this framework, the **CatBoost branch** captures global class dependencies through gradient-boosted decision ensembles, while the **CNN branch** extracts refined local spectral patterns using deep convolutional encoding. The fused outputs are processed by a **Prototypical Network** to learn a discriminative metric space and generate stable class prototypes for few-shot classification. An **Optimal Distortion Search (ODS)** mechanism is incorporated to enhance robustness against spectral distortions and optimize feature consistency.

A **sensitivity analysis** examines the effects of CatBoost hyperparameters, learning rate, and iteration count on model performance, evaluated using **accuracy**, **Kappa coefficient** (label agreement), and **Adjusted Rand Index (ARI)** (clustering quality). Cat-FSL consistently outperforms baseline few-shot models (Base-FSL, Aug-FSL) and traditional classifiers (XGBoost, AdaBoost, CatBoost).

Experiments on benchmark **Indian Pines** and **Salinas** datasets demonstrate Cat-FSL’s ability to handle high spectral dimensionality, limited labeled data, and spectral overlap. The model preserves **spatial heterogeneity across scales** (validated through lacunarity analysis), generates **resilient prototypes** (high ARI), and enhances **inter-class margins** (verified by Prototype Separation Ratio and inter-class distance). Improved label agreement with ground truth is reflected by higher **Kappa scores**.

**Cat-FSL achieves state-of-the-art performance** with **98.92% accuracy on Indian Pines** and **98.19% on Salinas**, ensuring superior prototype stability, inter-class separability, and generalization under few-shot conditions. This demonstrates Cat-FSL’s potential as a robust **spectral-spatial meta-learning** framework that combines the interpretability of CatBoost with the representational power of CNNs for reliable HSI classification under data-scarce scenarios.
