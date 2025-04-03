# Identifying the Influence of Cryptococcus Growth Media, Time, and K-mer Motifs on GAT201 Effect in Gene Expression Modelling
A consulting project as part of a dissertation presented for the degree of MSc in Statistics with Data Science.

# Goal
This report aims to identify experiment design factors and k-mer motifs that significantly affect GAT201 effect on gene expression of Cryptococcus. Specifically, This report aims to answer the following two research questions.
1. Which experiment design factors, i.e., growth media condition and amount of time passed after
inoculation, significantly affect the GAT201 effect on gene expression level?
2. Which k-mer motifs significantly affect the GAT201 effect on gene expression level?

# Overview
Gene expression data of 6795 Cryptococcus neoformans genes and the frequencies
of k-mer motifs were provided. Design factors include time samples were taken (0, 30, 120, or 240 minutes
after inoculation), presence of GAT201 (WT if GAT201 is present or del if GAT201 is deleted), and
growth media (YPD, RMPMI, or RPMI with serum) with 4 replicates of each sample.

Differential Gene Expression (DGE) analysis with DESeq2 was conducted by constructing generalised
linear models (GLM) for each gene and assuming gene counts follow a negative binomial (NB) distribution.
Design factors are deemed influential on the GAT201 effects when for many genes, the interaction
term between them and GAT201 are significant. Then, gene expressions were modelled with k-mer motifs
frequencies and design factors as features to obtain small sets of influential motifs. To avoid computational
issues, a three-stage procedure is proposed: LFC computation with DGE analysis, motifs reduction
with Lasso regression, and model fitting with GLM. Variables of interest are the interaction terms between
motifs and GAT201. Finally, motif clustering was also done as a demonstration of dealing with
multicollinearity. Model comparison was done with AIC to measure the models’ performances.

# Content
* fungal_adlensius_report.pdf is the full report
* the final_fungal.Rmd is the main notebook consisting of all the codes to produce models, results, and graphics in the full report.
Note: Not all codes and results produced in the notebook is used in the main report. Some are simply for sanity checks.
* counts_all.csv is the gene counts data
* Gat201_samplesheet.csv is the metadata describing the samples code
* The remaining csv files with file names starting with H99 are the k-mer motifs frequencies data

# Author
This dissertation is authored by Adlensius Fransiskus Djunaedi

Supervised by Dr Natalia Bochkina and Dr Simon Taylor
