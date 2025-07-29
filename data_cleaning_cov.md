# paindata_cleaning_cov
## Section 1.0 Path ----
path_cov <- "~data/covariates/"

## Section 2.0 Data ----
## 2.1.0 data input:cov----
library(data.table)
cov <- as.data.frame(fread(paste0(path_cov,"cov_pain.csv")))
cov$Income  <- ifelse (cov$Income < 0, NA, cov$Income)
cov$PA  <- ifelse (test = c(cov$PA != 0.0), yes = 1, no = cov$PA)
cov$Qualification <- ifelse (cov$Qualification < 0, NA, cov$Qualification)
cov$Smoking <- ifelse (cov$Smoking < 0, NA, cov$Smoking)
cov$Alcohol <- ifelse (cov$Alcohol < 0, NA, cov$Alcohol)
cov$Medication <- ifelse (cov$Medication == 1,1,cov$Medication)
cov$Medication <- ifelse (cov$Medication == 2,1,cov$Medication)
cov$Medication <- ifelse (cov$Medication == 3,1,cov$Medication)
cov$Medication <- ifelse (cov$Medication == 4,0,cov$Medication)
cov$Medication <- ifelse (cov$Medication == 5,0,cov$Medication)
cov$Medication <- ifelse (cov$Medication == 6,0,cov$Medication)
cov$Medication <- ifelse (cov$Medication == -7,0,cov$Medication)
cov$Medication <- ifelse (cov$Medication == -1,NA,cov$Medication)
cov$Medication <- ifelse (cov$Medication == -3,NA,cov$Medication)

cov$Ethnicity <- ifelse (cov$Ethnicity < 0, NA, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 1001,1, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 2001,1, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 3001,1, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 4001,1, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 2,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 3,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 4,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 5,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 6,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 1002,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 2002,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 3002,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 4002,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 1003,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 2003,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 3003,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 4003,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 1004,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 2004,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 3004,0, cov$Ethnicity)
cov$Ethnicity <- ifelse (cov$Ethnicity == 4004,0, cov$Ethnicity)



write.csv(cov,file = paste0(path_cov,"cov_pain_new.csv"),row.names = F)
