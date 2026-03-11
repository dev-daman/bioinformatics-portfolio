# RNA-Seq Analysis of Human Airway Smooth Muscle Cells

## 🧬 Project Overview
This project identifies genes regulated by **Dexamethasone** in human airway cells to understand asthma treatment mechanisms. 

## 🛠️ Technical Stack
- **Language:** R (Bioconductor)
- **Primary Tool:** `DESeq2` for statistical modeling.
- **Visuals:** `ggplot2` and `pheatmap`.

## 📊 Key Results
### 1. Volcano Plot
This plot shows the relationship between statistical significance and the magnitude of change (Log2 Fold Change).
![Volcano Plot](volcano_plot.png)

### 2. Expression Heatmap
The heatmap shows the top 20 most significant genes across all 8 samples (Treated vs Control).
![Heatmap](heatmap.png)

## 🚀 Impact
The analysis successfully identified key regulatory genes like *CRISPLD2*, providing computational proof of the drug's anti-inflammatory effects.

