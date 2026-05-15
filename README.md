# Analyzing Gene Expression via PCA

This repository contains a computational analysis of the **GSE5325** dataset, as featured in the Nature Primer ["What is principal component analysis?"](https://www.nature.com/articles/nbt0308-303). The project focuses on using **Principal Component Analysis (PCA)** to reduce the dimensionality of transcriptomic data and visualize the biological differences between breast cancer subtypes.

The primary objective is to demonstrate how high-dimensional gene expression profiles can be compressed into principal components that retain clinical relevance.

## Dataset Overview

The analysis utilizes 105 patient samples organized into the following files:

* **`filtered.tsv.gz`**: A compressed matrix containing the expression levels of the complete gene set.
* **`class.tsv`**: Binary classification labels where `1` represents **ER+** (Estrogen Receptor positive) and `0` represents **ER-** (Estrogen Receptor negative) breast cancer.
* **`columns.tsv.gz`**: A mapping reference used to link numerical IDs (e.g., ID 4404) to their respective Gene Symbols (e.g., **XBP1**).

## Project Methodology

1.  **Feature Selection**: We identified and isolated the expression values for key biomarkers **XBP1** and **GATA3**.
2.  **2D Correlation (Figure 1a)**: A scatter plot was constructed to evaluate how these two genes correlate with one another and how they distribute across the two clinical classes.
3.  **PCA Implementation**: We used the `scikit-learn` library to compute the first Principal Component (**PC1**), effectively finding the linear combination of the two genes that captures the most variance.
4.  **1D Projection (Figure 1c)**: By projecting the 2D data onto the PC1 axis, we visualized the separation efficiency of the reduced feature set.

## Findings
* **Dimensionality Reduction**: PCA successfully identified a single axis (PC1) that maintains the clear separation between ER+ and ER- patients.
* **Biological Signaling**: The high variance captured by PC1 confirms that the expression patterns of **GATA3** and **XBP1** are significant indicators of the Estrogen Receptor phenotype.

## Requirements & Environment

The analysis is implemented in a Python-based Jupyter Notebook (`PCA_Analysis.ipynb`) using the following libraries:
* **Data Science**: `pandas`, `numpy`
* **Machine Learning**: `scikit-learn`
* **Visualization**: `matplotlib`, `seaborn`

## Running the Project

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Akash2512-Sagar/pca
   cd pca
