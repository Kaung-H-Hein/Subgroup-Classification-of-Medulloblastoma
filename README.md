# Subgroup-Classification-of-Medulloblastoma
This repository focuses on developing a classification model for subgrouping of medulloblastoma using Illumina 450K methylation data. The project was undertaken as part of my MSc Artificial Intelligence dissertation, during which I authored a research paper alongside a software package. While this repository highlights the core concepts of the project, the complete development—implemented in R—cannot be shared in compliance with University Guidelines of Queen's University Belfast.

## Abstract
Medulloblastoma, the most common malignant brian tumor, predominantly occur in children is categorized into four primary molecular subgroups: WNT, SHH, Group 3, and Group 4 each exhibiting significant molecular heterogeneity and varied survival outcomes. Accurate classification of these subgroups is crucial for optimizing treatments and improving patient outcomes. Based on the 2017 publication by E. C. Schwalbe et al., this study proposes a supervised machine learning-based approach using a DNA methylation profiling technique.

## Model 
The proposed model utilized methylation data obtained from Illumina 450K methylation microarray to classify medulloblastoma samples into into seven molecular subgroups: **WNT, SHH-Infant, SHH-Old/Child, Group3-LowRisk, Group3-HighRisk, Group4-LowRisk, and Group4-HighRisk**, incorporating age and risk factors for enhanced subgroup differentiation. It leverages six metagenes, capturing the underlying methylation patterns of the top 10,000 CpG probes with the highest variances, enhancing methylation data representation while reducing computational demands.

## Outcome 
Among the models evaluated, the SVM achieved the highest performance, with a mean accuracy of 98% on test data. Integrating this model into clinical decision-making could enhance subgroup-directed therapies and improve patient outcomes.

## Web Analysis Tool
The developed classification model is integrated into MBSC-450K, a prototype web analysis tool for Medulloblastoma Subgroup Classification, built with Shiny R. It is accessible at https://eeecs.shinyapps.io/450k_mb_classification/.

## Dataset 
The 450K methylation dataset, GSE93646, retrieved from the Gene Expression Omnibus (GEO) public repository provided by the National Center for Biotechnology Information (NCBI), includes 428 medulloblastoma samples, which will be used for model training and testing. The dataset contains processed beta values, representing the proportion of DNA methylation at specific CpG sites, with values ranging from 0 (unmethylated) to 1 (fully methylated). Additionally, detection p-values are provided, indicating the confidence in the methylation measurements at each CpG site, with lower p-values reflecting higher confidence in the data. Each dataset comprises 485,512 rows corresponding to CpG probes, with columns representing sample IDs and their respective detection p-values.

## Project Overview
This project is primarily divided into three key parts:

### Key Libraries and Tools Used
- **Pandas**: Data manipulation and analysis.
- **NumPy**: Numerical operations and array handling.
- **Matplotlib & Seaborn**: Data visualisation (plots, charts, etc.).
- **Scikit-learn**: Machine learning library for feature selection, preprocessing, model building, and evaluation. Key functions used:
- **VarianceThreshold** (feature selection)
- **NMF, PCA, TSNE** (dimensionality reduction)
- **MinMaxScaler** (scaling)
- **train_test_split** (data splitting)
- **SVC, KNeighborsClassifier, RandomForestClassifier, GradientBoostingClassifier** (classification models)
- **GridSearchCV, StratifiedKFold, learning_curve** (model optimisation and evaluation)
- **accuracy_score, classification_report, confusion_matrix** (model performance metrics)

### 1. Data Preprocessing
- **Dropping unnecessary columns**: Removing columns that do not contribute to the model’s predictive power.
- **Concatenating data with subgroup labels**: Merging methylation data with corresponding subgroup labels for supervised learning.
- **Calculating variance of CpG probes**: Evaluating the variability of each CpG probe to identify informative features.
- **Feature selection for the top 10K CpG probes**: Selecting the most informative CpG probes for model training.
- **Handling missing data**: Applying appropriate methods (e.g., imputation) to address missing values in the dataset.
- **Applying label encoding**: Converting categorical labels into numerical format for model compatibility.
- **Extracting metagenes using Non-negative Matrix Factorization (NMF)**: Reducing dimensionality and summarising methylation patterns into metagenes.
- **Creating visualisations**: Generating visual representations of the data and results (e.g., heatmaps, box plots).
- **Performing Principal Component Analysis (PCA) with scatterplots**: Reducing data dimensions and visualising variance across samples.
- **Conducting t-SNE analysis with scatterplots**: Further dimensionality reduction to capture complex structures in the data.

### 2. Model Development
- **Model Selection from SVM, k-Nearest Neighbours (KNN), Random Forest (RF), and Gradient Boosting Classifier**: Choosing appropriate machine learning algorithms for classification based on performance and characteristics.
- **Optimising models using GridSearchCV**: Tuning hyperparameters to enhance model performance through cross-validation.

### 3. Model Evaluation
- **Evaluating model performance on a test set**: Assessing how well the model generalises to unseen data.
- **Calculating performance metrics including precision, recall, F1 score, and support**: Quantifying the model’s performance using various evaluation metrics.
- **Generating confusion matrices**: Visualising classification results to assess true/false positives and negatives.
- **Validating models using stratified k-fold cross-validation**: Ensuring robust validation by splitting the data into k subsets, maintaining consistent class distributions.
- **Creating learning curves to assess generalisability**: Plotting performance against training size to evaluate overfitting or underfitting.
