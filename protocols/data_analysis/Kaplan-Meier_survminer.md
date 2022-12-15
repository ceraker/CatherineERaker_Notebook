# __Kaplan-Meier Analysis Base Code__
#### Author: Cassie Raker
#### Last updated: December 15, 2022

#### Data uploaded and analyzed in R Studio

##### Code modified from cheat sheet from https://github.com/kassambara/survminer/


Load packages
```{r}
library(tidyr)
library(dplyr)
library(lubridate)
library(survival)
library("survminer")
```

Read in and format your data (make sure you have a column for whether or not each data point is censored: this should be binary)
```{r}
#load survminer formatted field data
survminer_field <- read.csv("2019_PR_survminer_field.csv")

#reformat all dates to POSIXt format using lubridate and delete old columns
survminer_field$ymd.planted=mdy(survminer_field$date.planted)
survminer_field$ymd.mortality=mdy(survminer_field$date.of.mortality)
survminer_field <- select(survminer_field, -date.planted, -date.of.mortality)

#calculate number of days between planting and mortality
survminer_field$days.alive <- difftime(survminer_field$ymd.mortality ,survminer_field$ymd.planted , units = c("days"))
```

Create survival and survfit objects
```{r}
Surv(survminer_field$days.alive, survminer_field$censored)

surv_object <- Surv(survminer_field$days.alive, survminer_field$censored)
```

Create plot!
```{r}
#Kaplan-Meier field data plots separated by genotype
fit2 <- survfit(surv_object ~ genotype, data = survminer_field)
s3 <- ggsurvplot(fit2, data = survminer_field, pval = TRUE, legend = "bottom", legend.title = "Genotype", legend.labs = c("AZ","BY","CX","DW","EV","FU","GT","HS","IR","JQ"))
s3 <- s3 + guides(colour = guide_legend(nrow = 2))
s3 <- s3 + xlab("Days")
s3
```
If you want to cut off all curves at the same point the lazy cheater way:
```{r}
s3 <- ggsurvplot(fit2, data = survminer_field, pval = TRUE, legend = "bottom", legend.title = "Genotype", legend.labs = c("AZ","BY","CX","DW","EV","FU","GT","HS","IR","JQ"), xlim = c(0, 85))
```
