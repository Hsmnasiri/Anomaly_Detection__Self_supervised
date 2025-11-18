# Semi-Supervised Ensemble Framework for IoT Network Anomaly Detection

This repository accompanies the paper **"A Semi-Supervised Ensemble Framework for IoT Network Anomaly Detection"**, which proposes a hybrid learning pipeline that blends self-supervised representation learning with supervised classification through soft voting. The approach targets intrusion detection in Internet of Things (IoT) networks, where labeled attack data are scarce and expensive to curate.

## Research Motivation
Modern IoT infrastructures expand the cybersecurity attack surface but lack abundant high-quality labels for intrusion events. Purely supervised detectors struggle with concept drift and unseen threats, while single-paradigm semi-supervised or self-supervised methods can overfit to specific attack modes or fail to translate learned embeddings into accurate classifiers. The paper addresses this gap by unifying both paradigms in a single ensemble to increase robustness and reduce dependence on manual annotation.

## Proposed Framework
The framework operates in two coordinated stages:

1. **Self-supervised feature extraction** – A self-supervised learner is trained on unlabeled network traffic to derive rich embeddings that capture temporal and structural patterns without manual labels.
2. **Supervised classification** – A high-performing supervised model is trained on the limited labeled subset of the data to predict normal versus malicious activity.
3. **Soft-voting ensemble** – Predictions from the self-supervised embedding-based model and the supervised classifier are fused via soft voting, leveraging confidence scores to balance recall and precision across diverse attack types.

This integration mitigates labeling costs while improving generalization to evolving threats.

## Dataset and Experimental Design
Experiments rely on the heterogeneous **ToN-IoT** dataset, evaluating both anomaly-majority and normal-majority settings to mirror real deployment conditions. The study reports improvements in F1-Score and ROC-AUC over individual baselines, demonstrating the ensemble’s ability to preserve detection performance while remaining scalable to large traffic corpora.

## Key Contributions
- Bridges self-supervised representation learning with supervised decision-making in a unified ensemble, minimizing reliance on labeled network traffic.
- Employs soft voting to integrate complementary confidence estimates, enhancing robustness under varying attack distributions and operational conditions.
- Provides empirical validation on ToN-IoT across imbalance scenarios, illustrating scalability and adaptability for real-world IoT security monitoring.

## Repository Contents
- `Anomaly_Detection__Self_supervisedPaper.pdf`: Full paper detailing methodology, experiments, and results.
- `Anomaly_Detection__Self_supervised.pdf`: Supplementary version of the paper.

## Getting Started
1. **Review the paper** in `Anomaly_Detection__Self_supervisedPaper.pdf` for methodological details and experimental settings.
2. **Reproduce experiments** by implementing the self-supervised encoder, supervised classifier, and soft-voting ensemble described above using the ToN-IoT dataset. Focus on handling both anomaly-majority and normal-majority splits to mirror the reported evaluation.
3. **Extend the work** by exploring alternative self-supervised objectives or ensemble weighting schemes to further reduce reliance on labeled data and improve resilience to concept drift.

## Citation
If you build upon this study, please cite the paper:

> Mina Erfan, Sahil Khokhar, Hesam Nasiri, and Sadra Teymourian. "A Semi-Supervised Ensemble Framework for IoT Network Anomaly Detection." University of Ottawa. 2024.
