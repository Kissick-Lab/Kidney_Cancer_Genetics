# Kidney Cancer Genetics

This repository contains code and resources for analyzing genetic data related to kidney cancer

## Folder Structure
### assign_purity_and_clonality
Contains code in a qmd file to assign purity and clonality for each mutation. 

1_binomial_assignment.qmd: Contains code to fit mutations with 2 copies and 1 copy into a binomial distribution model

2_purity_calculator.qmd: Contains code to calculate the purity associated with each mutation

3_clonality.qmd: Contains code to calculate Clonal and Subclonal P-values for each mutation, providing an assessment of mutation clonality

### clonality_matcher
Contains code in a qmd file to match the same mutations between ENPP3lo and ENPP3hi cells, enabling downstream analysis of clonality relationship


## Input data
The code utilizes genetic data from a patient (ID: K416) as an example dataset for analysis
