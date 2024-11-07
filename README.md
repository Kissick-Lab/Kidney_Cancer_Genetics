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

### clonality_relationship
Contains code in a qmd file to assign clonality relationship to each mutation

## Input data
The code utilizes genetic data from a patient (ID: K416) as an example dataset for analysis

The following instructions outline the analysis each sample undertook and will generate output files of raw data corresponding to figures in the paper.

1.	Binomial Assignment:
   
   This takes a VCF output file from the standard alignment, mutation calling, filtering, etc. and fits 2 or 3 binomial distributions to the data (See methods figure A).

Input Files:
/assignmen_purity_and_clonality/input/snvs/*.csv

Output files: 

Generated file contains the mean and magnitude of these binomal fits for regions with 1-copy and 2-copies of DNA.

3.	Purity assesment:
   
   This takes the output files from the binomial assignment script and calculates the purity of each sample (See methods for full explanation)

Input Files:
Output file from 1. Binomial Assignment

Output file:
Purity file containing value for each sample

4.	Clonality:
   
   This script takes the original csv file and calculates the probability each mutation belongs to a clonal or sub-clonal mutation distribution.

Input files:
Files in /assignmen_purity_and_clonality/input/snvs/*.csv
Purity file generated in the previous script

Output file:
Same file format as the input .csv file, but now contains statistics for each mutation on the likelihood it belongs to the clonal or sub-clonal distributions

5.	Clonality Matcher:
   
	This script takes the ENPP3hi and ENPP3lo files from each patient and outputs a file with the frequency and other details of each mutation in each sample.

Input files:
Output from the clonality script for both ENPP3hi and ENPPlo cells from 1 patient

Output file:
file containing data on each mutation from ENPP3lo and ENPP3hi cells from the same patient

6. Mutation relationship
   This script analyzes the matched mutations and determines how each given mutation changes between the ENPP3lo and ENPP3hi state.
   Also generates figures shown in figure 1

Input files:
Output from Clonality Matcher

