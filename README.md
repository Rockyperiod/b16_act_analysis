# b16_act_analysis
## Overview
We developed ODE-based mathematical models to describe the dynamics of tumor growth and immune response in the context of adoptive cell therapy (ACT) in a B16F10 melanoma mouse model. 
In parallel, we performed multi-omics analyses to uncover counter-regulatory mechanisms that affect the efficacy of ACT.

## Structure

### Code
- `code/ode` : 
  - `00_data_preprocessing.ipynb` : Data formatting and preprocessing  
  - `01S_untreated_model_comparison.ipynb` : Comparison of multiple models for untreated tumor dynamics and selection of the optimal model
  - `01_untreated_model.ipynb` : Modeling tumor and tumor-infiltrating myeloid cells (TIM) growth in untreated mice  
  - `02_tst_model.ipynb` : Modeling tumor-specific T cell (TST) therapy with parameter optimization
  - `03_fractionate_dosing.ipynb` : Simulations of fractionated dosing  
  - `04_adaptive_dosing.ipynb` : Simulations of adaptive dosing strategies  

- `code/microarray` :
  - `05_microarray.ipynb` : Time-course analysis of ACT using microarray data

- `code/sc_rna` :
  - `06_01_merge.ipynb`: Quality control and data merging
  - `06_02_preprocessing.ipynb`: Global clustering of CD45⁺ immune cells
  - `06_03_annotation.ipynb`: Annotation of global clusters
  - `06_04_GSEA_analysis.ipynb`: Gene set enrichment analysis
  - `06_05_TIM_subclustering.ipynb`: Subclustering of tumor-infiltrating myeloid cells (TIMs)
  - `06_06_GO_analysis.ipynb`: Gene Ontology enrichment analysis  

### Data
- `data/tumor/` : B16F10 tumor volume datasets
- `data/immune/` : Immune cell counts from B16F10 tumor-bearing mice  
- `data/microarray/` : Placeholder for microarray dataset ([GSE57304](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE57304); raw data not included)  
- `data/sc_rna/` : Placeholder for single-cell RNA-seq dataset ([GSE299448](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE299448); raw data not included)  

## Requirements
This project uses Docker containers for reproducibility. Two separate environments are used depending on the analysis module:

- **ODE modeling(code/ode_model) and microarray analysis(code/microarray)** → ([jupyter/scipy-notebook:python-3.11](https://hub.docker.com/r/jupyter/scipy-notebook))

- **Single-cell RNA-seq analysis(code/sc_rna)** → ([rnakato/shortcake_r:3.3.0](https://hub.docker.com/r/rnakato/shortcake_r))