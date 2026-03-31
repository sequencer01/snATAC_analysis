# snATAC_analysis
The analysis workflow of glioma snATAC-seq data 
This repository contains an R pipeline for analyzing single-cell ATAC-seq data using the ArchR package, including quality control, clustering, integration with scRNA-seq data, peak calling, motif analysis, and trajectory inference.

## Overview

The pipeline performs the following steps:
1. **Data Import & Arrow File Creation** - Convert fragment files to ArchR Arrow format
2. **Quality Control** - Filter doublets and low-quality cells based on TSS enrichment and fragment counts
3. **Dimensionality Reduction** - LSI and UMAP embedding
4. **Clustering** - Graph-based clustering using Seurat
5. **Integration with scRNA-seq** - Label transfer from reference single-cell RNA data
6. **Batch Correction** - Harmony integration for sample/batch correction
7. **Peak Calling** - Cell-type specific peak identification using MACS2
8. **Motif Analysis** - TF motif enrichment and deviation analysis
9. **Trajectory Analysis** - Pseudotime inference between cell states

## Requirements

### R Packages
```r
library(Seurat)
library(dplyr)
library(Matrix)
library(ggplot2)
library(tidyr)
library(RColorBrewer)
library(ArchR)
library(viridis)  # Required for heatmap color palette
library(ggrepel)  # Required for motif enrichment plots
