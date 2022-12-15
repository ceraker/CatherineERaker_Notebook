# __RStudio Cheat Sheet__
#### Author: Cassie Raker
#### Last updated: November 17, 2022


###### Select from one dataframe (df1) using a column/list from another dataframe (df2)

in dplyr
```{r}
df1 %>%
      filter([column in df1] %in% df2$[column in df2])
```
in base r
```{r}
subset(df1, [column in df1] %in% df2$[column in df2])

#example
all_long_modgrey <- subset(all_long2, id %in% modgrey$id)
```

###### Aggregate long dataframe to wide dataframe
```{r}
#create new peak_norm data that is log transformed
all_long2$peak_norm <- log((all_long2$peak_stand + 1000))
```

```{r}
#create new dataset that has samples as rows and peak areas grouped by class
agg_comp <- aggregate(peak_norm ~ coralID + id, data = all_long2, FUN = sum, na.rm = TRUE)

#put in wide form so compound classes are column titles
agg_comp_wide <- spread(agg_comp, id, peak_norm)

#merge with metadata
agg_all <- merge(agg_comp_wide, meta2, by="coralID")

#remove unnecessary columns (dates etc)
agg_all <- agg_all[ -c(350:354)]

#make sure acclimation treatment and genotype columns are being read as factor
agg_all$ATTRIBUTE_acclimation <- as.factor(agg_all$ATTRIBUTE_acclimation)
agg_all$ATTRIBUTE_genotype <- as.factor(agg_all$ATTRIBUTE_genotype)
```

```{r}
#change the column order so descriptive columns are grouped at the beginning
#also remove coralID column (that info is redundant)
agg_all <- agg_all[ , c(346, 347, 348, 349, 2:345)]
View(agg_all)
```

```{r}
#save as csv
write.csv(agg_all,"agg_all.csv")
write.csv(agg_parent_norm_all, "agg_parent_norm_all.csv")
```
