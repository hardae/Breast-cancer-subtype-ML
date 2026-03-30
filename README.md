# Breast-cancer-subtype-ML
 A machine learning pipeline for classifying breast cancer molecular subtypes using TCGA gene expression data. Built as part of a structured bioinformatics learning curriculum. 

# Breast-Cancer-Subtype-ML 🧬

A machine learning pipeline for classifying breast cancer molecular subtypes using TCGA gene expression data. Built as part of a structured bioinformatics learning curriculum.

---

## Project Overview

Breast cancer is not a single disease — it comprises distinct molecular subtypes with different biological behaviours, treatment responses, and survival outcomes. This project builds a supervised machine learning classifier to predict **PAM50 breast cancer subtypes** from RNA-seq gene expression data.

### Subtypes Classified
| Subtype | Description | Samples |
|---------|-------------|---------|
| Luminal A (LumA) | ER+, low proliferation, best prognosis | 434 |
| Luminal B (LumB) | ER+, higher proliferation, more aggressive | 194 |
| Basal-like | Triple negative (ER−, PR−, HER2−), hardest to treat | 142 |
| HER2-enriched | HER2 overexpressed | 67 |

> Normal-like samples (n=119) were excluded due to their controversial biological interpretation.

---

## Dataset

**Source:** [UCSC Xena Browser](https://xenabrowser.net/datapages/) — TCGA Breast Cancer (BRCA) cohort

| File | Description |
|------|-------------|
| `TCGA.BRCA.sampleMap_HiSeqV2.gz` | Gene expression (RNA-seq, log2 RSEM normalized) |
| `TCGA.BRCA.sampleMap_BRCA_clinicalMatrix` | Clinical data including PAM50 subtype labels |

- **Total samples after filtering:** 837
- **Total genes:** 20,530
- **Genes after feature selection:** 2,000 (top variance)

> Dataset files are not included due to size. Download from [UCSC Xena](https://xenabrowser.net/datapages/?cohort=TCGA%20Breast%20Cancer%20(BRCA)).

---

## Pipeline

Raw Data → Data Loading → Filtering → Transpose Matrix → Merge Data
→ Feature Selection → Train/Test Split → Scaling → Random Forest → Evaluation


---

## Results

**Overall Accuracy: 86%**

| Subtype | Precision | Recall | F1-Score | Support |
|---------|-----------|--------|----------|---------|
| Basal | 1.00 | 1.00 | 1.00 | 29 |
| Her2 | 1.00 | 0.69 | 0.82 | 13 |
| LumA | 0.84 | 0.92 | 0.88 | 87 |
| LumB | 0.77 | 0.69 | 0.73 | 39 |

---

## Requirements
python >= 3.10
pandas
numpy
scikit-learn
matplotlib
seaborn

pip install pandas numpy scikit-learn matplotlib seaborn

## How to run
1. clone the repository
   git clone https://github.com/hardae/Breast-cancer-subtype-ML.git
cd Breast-Cancer-Subtype-ML
2. Download dataset files from UCSC Xena and place them in the project folder
	3.	Open and run the notebook top to bottom
    jupyter notebook brca_classification.ipynb

Project Context
This is Project 2 of a self-directed bioinformatics learning curriculum.
