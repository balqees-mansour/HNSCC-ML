# HNSCC Genomic Analysis and Osteoarthritis ML Pipeline

This repository showcases a comprehensive bioinformatics pipeline for Head and Neck Squamous Cell Carcinoma (HNSCC) analysis and a prototype machine learning pipeline for identifying regenerative gene factors in knee osteoarthritis (OA).

## Overview

This project is divided into two main parts:

1.  **HNSCC Genomic Analysis**: An in-depth analysis of TCGA-HNSC RNA-seq data, including differential expression analysis, batch effect correction, and gene set enrichment analysis (GSEA).
2.  **Osteoarthritis (OA) ML Pipeline**: A prototype machine learning pipeline designed to classify samples as OA vs. Healthy based on gene expression data. This pipeline is developed as a proof-of-concept for the identification of regenerative gene factors in knee osteoarthritis, as per the requirements of Kairos Therapeutics.

## Features

*   **HNSCC Analysis**:
    *   Differential expression analysis (DESeq2)
    *   Batch effect correction (sva)
    *   Gene Set Enrichment Analysis (GSEA) with KEGG and GO
    *   Visualization of results (PCA, volcano plots, heatmaps)
*   **OA Machine Learning Pipeline**:
    *   Data preprocessing and feature scaling
    *   Train-test split with stratification
    *   Implementation of ElasticNet and Random Forest models
    *   5-fold cross-validation
    *   Feature importance extraction
    *   Model performance evaluation (AUC, accuracy, confusion matrix)

## Project Structure

```
. HNSCC_OA_Project/
├── data/
├── notebooks/
│   └── OA_ML_Pipeline.ipynb
├── results/
│   └── plots/
├── scripts/
│   ├── all_HNSCC_tissues_Biomart.R
│   ├── batch_tcga.R
│   ├── CNV_HNSCC.R
│   ├── GSEAScript.R
│   └── ml_pipeline.py
└── README.md
```

## Installation

### R Dependencies

```R
# Install Bioconductor
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

# Install required packages
BiocManager::install(c("curatedTCGAData", "TCGAbiolinks", "SummarizedExperiment", "DESeq2", "sva", "clusterProfiler", "org.Hs.eg.db", "biomaRt"))
install.packages(c("ggplot2", "dplyr", "stringr", "forcats"))
```

### Python Dependencies

```bash
pip install pandas scikit-learn jupyter
```

## Usage

### HNSCC Analysis

The R scripts in the `scripts/` directory can be run to reproduce the HNSCC analysis. Please ensure that the file paths in the scripts are updated to your local environment.

### OA Machine Learning Pipeline

The machine learning pipeline can be run using the Jupyter notebook `notebooks/OA_ML_Pipeline.ipynb` or the Python script `scripts/ml_pipeline.py`.

```bash
python scripts/ml_pipeline.py
```

## HNSCC Analysis Results

### GSEA Results

**Top 15 GO: Biological Process**

![Top 15 GO: Biological Process](results/plots/WhatsAppImage2025-12-18at05.54.00.jpeg)

**Top 15 GO: Molecular Function**

![Top 15 GO: Molecular Function](results/plots/WhatsAppImage2025-12-18at05.54.00(2).jpeg)

**Top 15 GO: Cellular Component**

![Top 15 GO: Cellular Component](results/plots/WhatsAppImage2025-12-18at05.54.00(1).jpeg)

### Upregulated and Downregulated GO and KEGG Pathways

![Upregulated and Downregulated GO and KEGG Pathways](results/plots/WhatsAppImage2025-12-19at05.29.42.jpeg)

![Upregulated GO Terms](results/plots/WhatsAppImage2025-12-19at05.29.42(2).jpeg)

![Downregulated GO Terms](results/plots/WhatsAppImage2025-12-19at05.29.42(1).jpeg)

## Osteoarthritis (OA) Machine Learning Pipeline

This pipeline is designed to be a reproducible and interpretable machine learning workflow for classifying OA vs. Healthy samples. It uses a placeholder dataset and can be adapted to real-world gene expression data.

### Models

*   **ElasticNet**: A linear regression model with both L1 and L2 regularization, which is useful for feature selection.
*   **Random Forest**: An ensemble of decision trees that is robust to overfitting and can capture non-linear relationships.

### Evaluation

The models are evaluated using a stratified train-test split and 5-fold cross-validation. The performance metrics include AUC, accuracy, and a confusion matrix.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact

For any questions or feedback, please contact [Your Name] at [Your Email].
