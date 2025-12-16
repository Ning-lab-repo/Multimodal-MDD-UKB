# Multimodal-MDD-UKB
# Multimodal Data Integration for MDD Diagnosis and Risk Prediction

This repository contains the code and analysis pipeline for the study:  

**"Multimodal data integration for diagnosis and risk prediction of major depressive disorder in the UK Biobank"**  

## 1. Study Overview  

This study leverages multimodal data from the UK Biobank to develop machine learning models for:  
- Diagnostic classification of prevalent Major Depressive Disorder (MDD)  
- Prospective risk prediction of incident MDD over 15 years  

The analysis integrates six data modalities:  
- **Proteomics** (2,420 proteins)  
- **Metabolomics** (240 features)  
- **Clinical Biochemistry** (34 variables)  
- **Polygenic Risk Scores** (27 scores)  
- **Demographics & Early-Life Factors** (43 variables)  
- **Family History** (51 variables)  

## 2. Key Findings  

- **Lifestyle factors** and **proteomic features** consistently showed strongest performance  
- **Multimodal integration** substantially improved performance (AUC up to 0.791 for prevalent MDD)  
- **Distinct molecular signatures** for diagnostic vs predictive models  
- **PRS alone** demonstrated limited discriminative ability  
- **Stable prediction** over 15-year follow-up (mean AUC = 0.679)  


## 3. Installation and Setup  

### Prerequisites
- Python 3.10.16  
- R 4.5.0 (for enrichment analysis)    

### R Dependencies
Required R packages for enrichment analysis:  
- clusterProfiler  
- org.Hs.eg.db  
- STRINGdb  


## 4. Key Outputs

The pipeline generates:  
1. **Model performance metrics**: AUC, C-index, accuracy, sensitivity, specificity   
2. **Feature importance rankings**: SHAP values, information gain  
3. **Biological insights**: Enrichment results, PPI networks  
4. **Visualizations**: ROC curves, time-dependent AUC plots, SHAP summary plots  
5. **Statistical results**: p-values, confidence intervals, hazard ratios  

## 5. Reproducibility  

### Geographical Stratification  
- **Training**: Participants from England  
- **Validation**: Participants from Scotland and Wales  

### Feature Selection Workflow  
1. Correlation filtering (ρ > 0.5)  
2. Information gain ranking  
3. SHAP value assessment  
4. Sequential forward selection (Delong test, p < 0.05)  

### Model Evaluation  
- 95% confidence intervals via 1,000 bootstrap iterations  
- Time-dependent AUC for incident prediction  
- External geographical validation  

## 6. Biological Databases  

- **STRING database** (v12.0): Protein-protein interactions  
- **Gene Ontology**: Functional enrichment  
- **KEGG**: Pathway enrichment  
- **UK Biobank**: Primary data source (application #347405)  


## 7. License  

This project is licensed under the MIT License - see the LICENSE file for details.  


## 8. Data Access

**Note**: UK Biobank data are available through a separate application process. This repository contains only the analysis code, not the raw data.  

## 9. Contact

For questions about the code, please open an issue in this repository.  

For scientific questions about the study, please contact the corresponding authors of the publication.  

---

*Last updated: December 2025*  
