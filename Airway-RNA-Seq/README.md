# 🧬 Airway RNA-seq Analysis

Differential gene expression analysis of the `airway` dataset using **DESeq2** in R — designed to run in Google Colab.

---

## 📖 Overview

This project analyzes the effect of dexamethasone (a glucocorticoid) treatment on airway smooth muscle cells using RNA-seq data. It identifies differentially expressed genes (DEGs) between treated and untreated samples.

> Dataset: [`airway`](https://bioconductor.org/packages/release/data/experiment/html/airway.html) — 8 samples from 4 human airway smooth muscle cell lines.

---

## 🔬 Workflow

```
Raw Counts (airway)
      ↓
Filtering (rowSums ≥ 10)
      ↓
DESeq2 Normalization & Modeling (~ cell + dex)
      ↓
Differential Expression (treated vs untreated)
      ↓
Visualization (PCA, Volcano, Heatmap, MA Plot)
      ↓
Export Results (CSV)
```

---

## 📊 Outputs

| Output | Description |
|--------|-------------|
| PCA Plot | Sample clustering by treatment and cell line |
| Volcano Plot | DEGs by fold change and significance |
| Heatmap | Expression patterns of top 30 DEGs |
| MA Plot | Log fold change vs mean expression |
| `DESeq2_all_results.csv` | Full results table for all genes |
| `DESeq2_significant_DEGs.csv` | Filtered DEGs (padj < 0.05, \|log2FC\| > 1) |

---

## 🚀 Getting Started

### Run in Google Colab (Recommended)

1. Go to [Google Colab](https://colab.research.google.com)
2. Create a new notebook
3. Change runtime: **Runtime → Change runtime type → R**
4. Copy and paste the script, then run

### Run Locally in R / RStudio

```r
# Clone the repo
# git clone https://github.com/your-username/airway-rnaseq-analysis.git

# Open airway_rnaseq.R in RStudio and run
```

---

## 📦 Dependencies

| Package | Source | Purpose |
|---------|--------|---------|
| `DESeq2` | Bioconductor | Differential expression analysis |
| `airway` | Bioconductor | Example RNA-seq dataset |
| `ggplot2` | CRAN | General plotting |
| `pheatmap` | CRAN | Heatmap visualization |
| `EnhancedVolcano` | Bioconductor | Volcano plot |

Install all dependencies:

```r
if (!requireNamespace("BiocManager", quietly = TRUE))
  install.packages("BiocManager")

BiocManager::install(c("DESeq2", "airway", "ggplot2", "pheatmap", "EnhancedVolcano"))
```

---

## 🗂️ Repository Structure

```
Airway-RNA-Seq/
│
├── Airway_RNA_Seq.ipynb               # Main analysis script
├── README.md                     # Project documentation
├── DESeq2_all_results.csv        # Generated after running script
└── DESeq2_significant_DEGs.csv   # Generated after running script
```

---

## 📈 Key Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| Design formula | `~ cell + dex` | Controlling for cell line |
| Reference level | `untrt` | Untreated as baseline |
| Min count filter | `rowSums ≥ 10` | Remove low-expressed genes |
| Significance cutoff | `padj < 0.05` | Adjusted p-value threshold |
| Fold change cutoff | `\|log2FC\| > 1` | 2-fold change minimum |

---

## 📚 References

- Love MI, Huber W, Anders S. *Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2*. Genome Biology, 2014. [doi:10.1186/s13059-014-0550-8](https://doi.org/10.1186/s13059-014-0550-8)
- Himes BE et al. *RNA-Seq Transcriptome Profiling Identifies CRISPLD2 as a Glucocorticoid Responsive Gene*. PLOS ONE, 2014. [doi:10.1371/journal.pone.0099625](https://doi.org/10.1371/journal.pone.0099625)

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

