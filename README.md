# Orthologous_deconvolution
---------------------------------------------------------------
Deconvolution of bulk data by detecting single cell outliers
---------------------------------------------------------------
Bulk RNA-seq data is prone to error due to sample impurity and existence of outlier cells. Single-cell data was used to clean up bulk samples in the following approach: Single-cell data from each organism was clustered using the MetaCell package (Baran et al., 2018). Clusters were manually annotated as microglia or outlier cell types, based on expression of core genes shared by all species. To account for cross-contamination of reads in the single cell datasets, we subtracted each average of clusters with high noise assumption of 10 % to remain with the strongest influencing genes. 
Each bulk sample can be described as a linear combination of all the cell types included in the samples. Therefore, we used R general-purpose optim function and the "L-BFGS-B" method to find optimal non-negative coefficients, depicting the relative contribution of each single cell cluster to the bulk sample. Then, we cleaned each bulk sample by subtracting the relative contribution of the outlier clusters.

Executing R script code in deconvolution_chicken.txt create the bulk file used in the paper.

