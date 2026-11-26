# NLP-prediction-modelling-study
R scripts of prediction model development and external validation study to assess the incremental predictive value of NLP-derived signs and symptoms for predicting 30-day all-cause hospitalization or mortality in patients aged ≥40 years presenting to general practice with lower respiratory tract infections.

# Elaborate information
This repository contains R scripts that were used in a prediction model development and external validation study among patients aged ≥40 years presenting to general practice with a lower respiratory tract infection (LRTI). This study assesses the incremental predictive value of natural language processing (NLP-)derived signs and symptoms for predicting 30-day all-cause hospitalization or mortality.

The publication of the study can be found via this link: (to be determined, currently submitted)

Inclusion criteria:
- Age ≥40 years at index date (i.e. LRTI diagnosis)
- General practitioner (GP) diagnosis of LRTI, defined as registration of either pneumonia (ICPC code R81) or acute bronchitis (ICPC code R78)

Outcome of interest:
- All-cause hospitalisation or mortality within 30 days from LRTI diagnosis
  
Cohorts derivation:
Model development: derived from the Julius General Practitioners' Network (JGPN) from the region of Utrecht, the Netherlands. Period: 2016 - 2019.
Model validation: derived from the Academic Network of General Practitioners Amsterdam (ANHA) from the region of Amsterdam, the Netherlands. Period: 2022 - 2023.
Statistical methods: Stepwise model development and external validation using elastic net penalized logistic regression. Four models were developed: basic model (age, sex, interaction term), basic + NLP model (basic + NLP-derived signs and symptoms), full model (basic model + cardiometabolic diseases, other medical history, medication use, and LRTI diagnosis code), and full + NLP model (full model + NLP-derived signs and symptoms).

Statistical analysis:
All models were internally validated by bootstrapping (1,000 samples). Subsequently, all models were externally validated in the ANHA cohort. Model performance was assessed and compared based on measures of discrimination (c-statistic), calibration (intercept and slope), distribution of predicted risks, and decision-curve analysis (upon external validation).

Information on R scripts published on this repository:

'Coefficients_final_model.csv' - csv-file containing predictor vales and full-precision coefficients of the final model
'0. R and package versions'
'1. Linkage_datacleaning_JGPN_CBS' - Script for linkage of JGPN primary care cohort to CBS hospitalization and mortality data, including datacleaning
'2. Linkage_datacleaning_ANHA_CBS' - Script for linkage of ANHA primary care cohort to CBS hospitalization and mortality data, including datacleaning
... tbd

Clean session execution procedure in R:

Apply for access to the respective data registries (JPGN, ANHA, DHD, and CBS - see 'availability of data' below)
Work within the secured remote research environment of CBS microdata
Open R script 1-5 in a clean R session
Check whether R and package versions are similar to those reported in script 0 ('R and package versions') on this repository
Run '1. Linkage_datacleaning_JGPN_CBS'
Run '2. Linkage_datacleaning_ANHA_CBS'
...tbd

The data that was used for this study is derived from the Dutch general practice registries (JGPN and ANHA), hospital registry (DHD), and the national mortality registry (CBS). Since these registries hold pseudonymised data on individual patients, access to these data is restricted and has been granted under license of this study. While metadata of the ELEMENT project have been published online via DataverseNL (https://doi.org/10.34894/UYHI95) and on this repository, the datasets cannot be made publicly available. Data are only available from the authors upon reasonable request and after formal permission of the respective registries (with further terms and conditions described in the DataverseNL metadata record of the ELEMENT project). Permission to access JGPN data can be requested at: https://www.juliushuisartsennetwerk.nl/onderzoekers/data-aanvraag-doen/. Permission to access ANHA data can be requested at: https://www.vumc.nl/zorg/informatie-voor-professionals/huisartsgeneeskunde-amsterdam-umc/academische-werkplaats-huisartsenzorg-amsterdam-noord-holland-almere/anha-informatie-voor-patienten.html. For DHD and CBS data specifically, these data are accessible for statistical and scientific research under certain conditions. For further information: https://www.cbs.nl/en-gb/our-services/customised-services-microdata/microdata-conducting-your-own-research.

Input data for scripts that are not publicly available:
Development_cohort.csv (primary care cohort file of development cohort)
Validation_cohort.csv (primary care cohort file of validation cohort)
Data on hospitalization (DHD registry) and mortality (CBS microdata registry)
