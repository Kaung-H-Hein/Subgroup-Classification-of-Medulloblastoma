# Subgroup-Classification-of-Medulloblastoma
This repository focuses on developing a classification model for subgrouping of medulloblastoma using Illumina 450K methylation data. The project was undertaken as part of my MSc Artificial Intelligence dissertation, during which I authored a research paper alongside a software package. While this repository highlights the core concepts of the project, the complete development—implemented in R—cannot be shared in compliance with University Guidelines of Queen's University Belfast.

## Abstract
Medulloblastoma, the most common malignant brian tumor, predominantly occur in children is categorized into four primary molecular subgroups: WNT, SHH, Group 3, and Group 4 each exhibiting significant molecular heterogeneity and varied survival outcomes. Accurate classification of these subgroups is crucial for optimizing treatments and improving patient outcomes. Based on the 2017 publication by E. C. Schwalbe et al., this study proposes a supervised machine learning-based approach using a DNA methylation profiling technique.

## Model 
The proposed model utilized methylation data obtained from Illumina 450K methylation microarray to classify medulloblastoma samples into into seven molecular subgroups: **WNT, SHH-Infant, SHH-Old/Child, Group3-LowRisk, Group3-HighRisk, Group4-LowRisk, and Group4-HighRisk**, incorporating age and risk factors for enhanced subgroup differentiation. It leverages six metagenes, capturing the underlying methylation patterns of the top 10,000 CpG probes with the highest variances, enhancing methylation data representation while reducing computational demands.

## Outcome 
Among the models evaluated, the SVM achieved the highest performance, with a mean balanced accuracy 98% and a macro-averaged AUC of 0.99 in an independent validation dataset of 276 samples. Integrating this model into clinical decision-making could enhance subgroup-directed therapies and improve patient outcomes.

## Web Analysis Tool
The developed classification model is integrated into MBSC-450K, a prototype web analysis tool for Medulloblastoma Subgroup Classification, built with Shiny R. It is accessible at https://eeecs.shinyapps.io/450k_mb_classification/.

## Project Overview
