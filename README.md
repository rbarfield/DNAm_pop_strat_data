Taken from https://web.archive.org/web/20181014233848/http://genetics.emory.edu/research/conneely/annotation-r-code.html

Annotation and R code for PC-based correction for population stratification in methylation data

R code to perform principal component analysis (PCA) of methylation data that has been subsetted to include only CpG sites near SNPs (based on the annotation files listed below): 

PCA_code.zip

This file contains two programs that are designed to be used together, in conjunction with one of the annotation files below.  The sample_code.R program calls the location.based.pc function in location.based.pc.R, which reads the selected annotation file and uses it to subset the methylation data before performing PCA.

sample_code.R is designed to be modified (or used as an example) by the user.  location.based.pc.R should not need to be modified except in special circumstances.

Annotation file of autosomal CpG sites from Illumina's 450K array that lie within 100 or fewer bp of a variant identified in the 1000 Genomes Project (Phase I) with MAF>.01 (based on all TGP samples):

    cpgs_within_100bp_of_TGP_SNP.Rdata
    cpgs_within_50bp_of_TGP_SNP.Rdata
    cpgs_within_10bp_of_TGP_SNP.Rdata
    cpgs_within_5bp_of_TGP_SNP.Rdata
    cpgs_within_2bp_of_TGP_SNP.Rdata
    cpgs_within_1bp_of_TGP_SNP.Rdata
    cpgs_within_0bp_of_TGP_SNP.Rdata
    cpgs_with_TGP_SNP_ON_PROBE.Rdata
    cpgs_with_TGP_SNP_ON_PROBE_within_10bp.Rdata

If using these files in conjunction with the R code provided above, simply download the chosen annotation file and provide its pathname in your location.based.pc function call (see sample_code.R).  The function will automatically read in and parse the data.

If using these files for some other purpose, note that each file contains an annotation data frame called 'a2'.  The first column of a2 is the list of CpG sites that can be used for subsetting data; the remaining columns contain additional annotation.

The above code and annotation are provided as supplementary material for our paper "Accounting for population stratification in DNA methylation studies":

Barfield RT, Almli LM, Kilaru V, Smith AK, Mercer KB, Duncan R, Klengel T, Mehta D, Binder EB, Epstein MP, Ressler KJ, Conneely KN (2014) Accounting for population stratification in DNA methylation studies. Genetic Epidemiology, Epub ahead of print. 

Annotation files were derived by comparing CpG position information from the Illumina 450K annotation to the publicly available 1000 Genomes Project data: http://www.1000genomes.org/

An integrated map of genetic variation from 1,092 human genomes, McVean et Al, Nature 491, 56–65 (01 November 2