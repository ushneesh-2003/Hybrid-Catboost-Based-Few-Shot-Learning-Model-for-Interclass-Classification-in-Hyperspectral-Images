# Hybrid-Catboost-Based-Few-Shot-Learning-Model-for-Interclass-Classification-in-Hyperspectral-Images
Cat-FSL is a hybrid CatBoost-based Few-Shot Learning model combining global CatBoost features and CNN spectral embeddings for robust HSI classification. It enhances inter-class separability via Prototypical Networks and Optimal Distortion Search.

🧠 Cat-FSL: Hybrid CatBoost-Based Few-Shot Learning for Hyperspectral Image Classification






Cat-FSL is a novel hybrid Few-Shot Learning (FSL) framework designed to enhance inter-class classification in Hyperspectral Images (HSI) under limited labeled data conditions.
The architecture combines CatBoost-derived global probabilistic features and CNN-based local spectral embeddings using a dual-path design, enabling robust prototype learning and superior class separability.

🚀 Key Features

Dual-Path Architecture:
Combines CatBoost (global dependencies) and CNN (local spectral refinement) for balanced feature representation.

Prototypical Network Fusion:
Merges both feature streams to learn a discriminative metric space and generate stable class prototypes.

Optimal Distortion Search (ODS):
Enhances robustness against spectral distortions and improves generalization.

Comprehensive Sensitivity Analysis:
Evaluates the effects of CatBoost hyperparameters, learning rate, and iteration count using:

Accuracy

Kappa Coefficient (label agreement)

Adjusted Rand Index (ARI, clustering quality)

📊 Performance Highlights

Datasets: Indian Pines, Salinas

Accuracy: 98.92% (Indian Pines) | 98.19% (Salinas)

Outperforms: Base-FSL, Aug-FSL, XGBoost, AdaBoost, and standalone CatBoost

Enhanced Metrics

Higher prototype resilience (↑ ARI)

Stronger inter-class separability (↑ Prototype Separation Ratio, inter-class distance)

Improved label agreement (↑ Kappa)

Preserved spatial heterogeneity (via lacunarity analysis)

🧩 Summary

Cat-FSL achieves state-of-the-art performance in few-shot HSI classification by integrating global CatBoost insights with local CNN-based spectral encoding.
It delivers robust generalization, resilient prototypes, and superior class discrimination under few-shot conditions, proving its potential as a reliable spectral-spatial meta-learning framework.
