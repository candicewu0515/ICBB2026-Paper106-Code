# LASSO-Based Gene Signature Identification for Colorectal Cancer Classification

This repository contains the analysis workflow accompanying ICBB 2026 Paper 106:

**LASSO-Based Gene Signature Identification for Colorectal Cancer Classification Using TCGA Expression Data**

Repository URL: https://github.com/candicewu0515/ICBB2026-Paper106-Code

## Overview

The workflow reproduces the main bioinformatics and machine-learning analysis:

- preprocessing of TCGA colorectal adenocarcinoma expression data
- differential expression analysis with `limma`
- PCA and unsupervised sample visualization
- heatmap and volcano plot generation
- LASSO logistic regression with `glmnet`
- ROC/AUC evaluation for lambda-minimum and lambda-1se models

## Data

The original local analysis used two tab-delimited files:

- `HiSeqV2`
- `TCGA.COAD.sampleMap_COAD_clinicalMatrix`

These filenames are consistent with the TCGA COAD sampleMap gene expression and clinical matrix files distributed through UCSC Xena. Because the raw expression matrix is a public third-party dataset and can be large, it is not stored in this repository.

Place the data files under:

```text
data/raw/
```

Expected paths:

```text
data/raw/HiSeqV2
data/raw/TCGA.COAD.sampleMap_COAD_clinicalMatrix
```

If downloading fresh data from UCSC Xena, use the TCGA COAD cohort and the corresponding `HiSeqV2` gene expression matrix plus COAD clinical matrix. If compressed files are downloaded, decompress them before running the R Markdown file.

## Reproducibility

Run the analysis from the repository root:

```r
rmarkdown::render("code/analysis.Rmd")
```

The workflow writes intermediate tables and figures to:

```text
results/
```

## Notes

The analysis was originally developed as a course/project workflow and was reorganized for conference-paper reproducibility. The paper reports the sample split used in the original analysis: 143 tumor samples and 186 adjacent normal samples, with 20,530 genes.
