# Research Internship – NicheNet Cell-Cell Communication Analysis

##  Project Overview
This project focuses on inferring cell-cell communications from single-cell RNA-seq (scRNA-seq) data using the **NicheNet R package** combined with **Seurat**.  
The analysis was performed on a **PBMC dataset**, with the aim of identifying key ligand-receptor interactions between **Dendritic Cells (DC)** as *sender cells* and **CD8 T Cells** as *receiver cells*.

The work is part of my research internship, and follows the methodology from the [NicheNet vignette](https://github.com/saeyslab/nichenetr/blob/master/vignettes/seurat_steps.md).

---

##  Methodology

### **Task 1 – scRNA-seq Preprocessing & Annotation**
- Data imported using `Read10X()` from the Seurat package.
- Quality control filtering based on:
  - Gene count (200–2500 unique genes per cell)
  - Mitochondrial gene percentage (<5%)
- Normalization with `LogNormalize()`
- Feature selection using `FindVariableFeatures()`  
- Dimensionality reduction via PCA and UMAP.
- Clustering using the Louvain algorithm with `FindClusters()`.
- Manual annotation using canonical marker genes.

### **Task 2 – NicheNet Analysis**
- Loading of prior knowledge models:
  - **Ligand–Receptor Network**
  - **Ligand–Target Matrix**
  - **Weighted Signaling & Gene Regulatory Networks**
- Identification of expressed genes in sender (DC) and receiver (CD8 T) cells.
- Selection of candidate ligands and their active receptors.
- Differential gene expression analysis in CD8 T cells using `FindMarkers()`.
- Prediction of ligand activities using `predict_ligand_activities()`.
- Visualization:
  - Top 30 active ligands (histogram & heatmap)
  - Ligand–Target interaction heatmap
  - Ligand–Receptor network heatmap

---

## Key Findings
- **Top Ligands:** IGFL3, IL4, IFNG predicted to have the most significant regulatory effect on CD8 T cells.
- **Active Receptors:** IFNGR1, IL4R, TNFRSF1B identified as key DC–CD8 communication mediators.
- **Ligand–Target Links:** 655 high-confidence interactions mapped.

---

## Repository Contents
- `scripts/` – R scripts for preprocessing and NicheNet analysis.
- `data/` – PBMC dataset (or download instructions).
- `figures/` – Plots generated during analysis.
- `README.md` – Project overview (this file).

---

## References
1. Browaeys, R., Saelens, W. and Saeys, Y. (2020) *NicheNet: modeling intercellular communication by linking ligands to target genes*. Nature Methods, 17, 159–162. https://doi.org/10.1038/s41592-019-0667-5  
2. Stuart, T. et al. (2019) *Comprehensive Integration of Single-Cell Data*. Cell, 177(7), 1888–1902.e21. https://doi.org/10.1016/j.cell.2019.05.031  
3. Seurat - https://satijalab.org/seurat/  
4. NicheNet GitHub - https://github.com/saeyslab/nichenetr  

---

## GitHub Pages
The live project documentation is available here:  
**[Research Internship Project Website](https://devaharish-03.github.io/Research-Internship/)**

---

## Author
**Devaharish Srikannan**  
Email: devaharish.srikannan@ucdconnect.ie
MSc Artificial Intelligence for Medicine and Medical Research,
School of Medicine,
University College Dublin  
