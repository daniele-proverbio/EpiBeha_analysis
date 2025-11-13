# EpiBeha_analysis

This repository contains the code and material to reroduce the results of the paper "Drivers of protective behaviours during epidemics", for the analysis of epidemic-behavioural aspects during COVID-19.

## Folders and files

The folders contain notebooks dedicated to each step of the analysis process, as decribed in the paper. For reproducibility, they should be run in the correct order, as they produce intermediate files that can be investigated for each step.

### FULL_DATA5_FINALE.csv
This is the **final constructed database**, resulting from the construction procedure described in the article and summarised in its Fig. 1. It consists in an integration of multiple public datasets (which are listed in the original article, and _should be referenced in case of re-use of this database_), after applyinng careful selection criteria to ensure its consistency and representativeness. The code to obtain this file is contained in the "database_construction" folder.

### "database_construction" 
It contains the code used to construct the integrated database. The intermediate files obtained through the procedure can be generated with the code or can be shared upon reasonable request. 

The external data are sometimes retrieved via APIs and sometimes come from existing CSV files available on relevant websites. The following links provide the CSV files needed for Phase 1:
* owid-covid-data.csv https://github.com/owid/covid-19-data/blob/master/public/data/owid-covid-data.csv
* positive-rate-daily-smoothed.csv https://ourworldindata.org/grapher/positive-rate-daily-smoothed
* face-covering-policies-covid.csv https://ourworldindata.org/grapher/face-covering-policies-covid
* covid-containment-and-health-index.csv https://ourworldindata.org/grapher/covid-containment-and-health-index
* time_series_covid19_US.csv https://github.com/govex/COVID-19/tree/master/data_tables/testing_data

* Note (for country.ipynb): The UMD Global CTIS API is _currently inactive_. However, it is possible to manually download the data from https://www.icpsr.umich.edu/web/ICPSR/studies/39206/versions/V3 .

All the CSV files must be placed in a dedicated "csv" folder for the scripts to function properly. During the execution of the scripts, additional CSV files will be generated and stored in the same folder. From country.ipynb and country-us.ipynb, two external tables will be generated (named Data and Dataus respectively). These contain CSV files with data retrieved via APIs.

The notebooks correspond to the various steps described in Table 1 of the manuscript, and should be run as ordered in the folder:

* 1-country.ipynb and 2-country-us.ipynb: they parse the UMD and US Delphi CTIS datasets and apply the temporal coverage and continuity criteria. Output: "us_mondo.csv" dataset with 90 countries.
* 3-samplesize.ipynb: sample size consistency criterion. Generates figures used in Supplementary Sec. 2
* 4-US_epidemiology.ipynb merges epidemic infos for US states with those about all the other countries
* 5-facebookdata.ipynb: analyses Facebook coverage Worldwide
* 6_coveragetest+CHI.ipynb: performs the analysis of epidemic indicators coverage, dynamics and statistics



## Credits
The code is adapted and refined from the one developed in https://github.com/scanta0705/Behaviours-and-contagion-during-the-COVID-19-pandemic-from-data-analysis-to-model-fitting/tree/main by Marie Scantamburlo.

If you wish to reuse the code, please cite its companion article: Scantamburlo, Proverbio and Giordano, "Drivers of protective behaviours during epidemics", 2025
