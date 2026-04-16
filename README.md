<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Columbia_University_shield.svg/200px-Columbia_University_shield.svg.png" width="120" alt="Columbia University Logo">
  
  # ML for Slime! 🦠 <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Columbia_University_shield.svg/200px-Columbia_University_shield.svg.png" width="190" alt="Columbia University Logo" valign="middle"> 
  **Predicting *Dictyostelium* Aggregation Centers using Deep Learning**
  
  *A project developed during my stay at **Columbia University***
</div>

---

## 👤 Author
**María Dolores Navarro Maturana (Lola)** — `mn3312`

## 🔬 Project Overview
*Dictyostelium discoideum* (affectionately known as "Dicty") is a fascinating slime mold. Alone, each cell acts as an independent organism. However, when starved, they release chemical signals (cAMP), creating spiral waves that prompt the cells to converge into a multicellular mound to explore territory and forage for food collectively. It is one of nature's first examples of multicellularity.

**The Objective:** Can we beat Dicty to its own meeting spot? 
This project leverages Convolutional Neural Networks (CNNs) to analyze the early spatio-temporal fingerprints of these cellular waves in microscopy movies. The goal is to predict the exact "aggregation center" long before the cells actually get there.

## 📂 Repository Contents

* 📓 **`slime_mold_mn3312.ipynb`**: The main Jupyter/Colab notebook. It contains the end-to-end pipeline for analyzing the Dictyostelium aggregation movies using CNN models, including data processing, training, and heatmap visualizations.
* 📓 **`HW2_pytorch_mn3312.ipynb`**: Contains all the foundational PyTorch implementations, answers, code, and figures corresponding to the theoretical coding exercises for the project's prerequisites.

## 📊 Data & Methodology

* **The Data:** Curated *Dicty disco shows*—cropped fields of view capturing different stages of aggregation and streaming as cells move. Provided by Allyson Sgro and Jennifer Hill from Janelia HHMI. Stored efficiently in chunked `Zarr` format.
* **The Task:** Using $N$ consecutive early frames, the model predicts either the exact coordinates of the eventual aggregation center or generates a spatial probability map (heatmap) of the likely zone.
* **The Approach:** Implementation of Deep Learning baselines ranked by spatial accuracy, focusing on extracting vector flow fields and interpretable motion cues from the time-lapse stacks.

## 📈 Evaluation Metrics
The models are benchmarked using the following criteria:
* **Center Error (μm):** Euclidean distance between the predicted hotspot and the ground-truth center.
* **Spatial Map Quality:** AUROC / Average Precision to evaluate how well the probability heatmap matches the true aggregation zone.
* **Resolution Robustness:** Evaluating the relative performance drop when the model is trained on high-resolution data but tested on subsampled data.

## 📚 References
* Sgro, A. E., et al. (2015). *"From intracellular signaling to population oscillations: bridging size‐and time‐scales in collective behavior."* Molecular Systems Biology, 11(1), 779.
* [Slime Mold Grows Network Just Like Tokyo Rail System | WIRED](https://www.wired.com/2010/01/slime-mold-grows-network-just-like-tokyo-rail-system/)
