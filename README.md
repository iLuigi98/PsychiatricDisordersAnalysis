# Psychiatric Disorders Analysis – RNA-Seq Replication & Tool Benchmark

## Overview

This project is a replication and exploration of the paper:  
**"Post-mortem molecular profiling of three psychiatric disorders"**  
by *Ramaker et al., Genome Medicine (2017)*

Our goals were:
- Replicate core transcriptomic findings comparing **schizophrenia (SZ)**, **bipolar disorder (BPD)**, **major depressive disorder (MDD)**, and controls
- Evaluate RNA-Seq tools such as **STAR** and **Kallisto** to determine trade-offs in speed, accuracy, and computational cost

## Motivation

Analyzing psychiatric disease at the molecular level requires large-scale RNA-Seq data and thoughtful tool selection. Different tools yield different alignments, affecting gene expression quantification, differential expression results, and ultimately the biological conclusions.

In this project, we examined:
- How choice of tools (STAR vs Kallisto) impacts output
- Scenarios where speed, cost-efficiency, or accuracy should be prioritized
- How improper tool choices can mislead research outcomes

## Project Structure
```
PsychiatricDisordersAnalysis/
├── LICENSE
├── Makefile           <- Makefile with commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   │
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models         <- Scripts to train models and then use trained models to make
│   │   │                 predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
│
└── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io
```


## Methods & Data

- **Transcriptomic Data**: Modeled after the post-mortem RNA-Seq data used in the original study
- **Brain Regions**:
  - Anterior Cingulate Cortex (AnCg)
  - Dorsolateral Prefrontal Cortex (DLPFC)
  - Nucleus Accumbens (nAcc)

- **Tools Used**:
  - `STAR` – high accuracy aligner, slower and resource-intensive
  - `Kallisto` – fast, pseudoalignment-based, lower sensitivity
  - `DESeq2` – for differential gene expression
  - `R` and `Python` – for data processing, visualization


## 🔍 Key Findings (Replication Summary)

- Most significant gene expression changes occurred in **SZ** patients, especially in the **AnCg**
- **EGR1** was significantly downregulated in SZ across cohorts, suggesting regulatory disruption
- Gene sets showed:
  - **Depletion of neuron-specific transcripts**
  - **Enrichment of astrocyte-specific transcripts** in SZ and BPD
- GABA-related metabolites aligned with reduced expression of GAD1/GAD2 enzymes


## Tool Comparison Summary

| Tool      | Accuracy       | Speed         | Best Use Case                       |
|-----------|----------------|---------------|-------------------------------------|
| STAR      | ⭐⭐⭐⭐⭐ High     |  Slower      | Research prioritizing precision     |
| Kallisto  | ⭐⭐ Moderate    |  Very Fast   | Large-scale or exploratory datasets |

We observed that STAR provides more reliable mapping at a higher cost, while Kallisto is better for fast, exploratory studies.


## Technologies & Skills

- RNA-Seq Analysis & Alignment  
- STAR vs Kallisto benchmarking  
- Differential Expression with DESeq2  
- PCA & Cluster Analysis  
- Python (pandas, seaborn), R  
- Git & GitHub version control

##  Paper Reference

**Ramaker et al. (2017)**  
[Post-mortem molecular profiling of three psychiatric disorders](https://doi.org/10.1186/s13073-017-0458-5)  
*Genome Medicine, 9, 72 (2017)*

## 👤 Authors

**Luigi Cheng**  
M.S. Data Science (UCSD, in progress)  
GitHub: [@iLuigi98](https://github.com/iLuigi98)  
Portfolio: [luigidata.com](https://luigidata.com)




**Dennis Wu**  
M.S. Computer Science (UCSD)  
GitHub: [@denncc](https://github.com/denncc) 

