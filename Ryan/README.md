GLMBoosted Regression on Event Free Survival Time 

Input data was cleaned and prepared as outlined on the main README. 

WT dataset (https://github.com/NCBI-Hackathons/RNAseq_Cancer_Biomarkers/blob/master/scripts/WT_assay_clinical.csv.zip)

First distribution of Event Free Survial Time in Days (EFST) was plotted and the median (331 days) calculated. ![Distribution_of_EVST_median](https://github.com/NCBI-Hackathons/RNAseq_Cancer_Biomarkers/blob/master/Ryan/Distribution_of_EVST_median.pdf) The data was then bisected on the median into two cohorts. Then each normalized gene expression data was averaged for each cohort and the difference between each cohort calculated. ![Log_variance_plot](https://github.com/NCBI-Hackathons/RNAseq_Cancer_Biomarkers/blob/master/Ryan/log_variance_plot.pdf). Then I removed the genes which had a variance from zero of less than 0.05.

Next, I split the data in half into test and training sets and used [R MLR package](https://mlr.mlr-org.com/) to build a GLM boosted regression model predicting EVST based off expression of the genes that survivied the variance trimming. 