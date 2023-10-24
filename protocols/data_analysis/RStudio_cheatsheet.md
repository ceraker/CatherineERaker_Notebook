# __RStudio Cheat Sheet__
#### Author: Cassie Raker
#### Last updated: August 6, 2023


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

###### Select Rows based on Column Value
```{r}
# Select Rows by column value
df[df$gender == 'M',]

# Select Rows by Checking values on Multiple Columns
df[df$gender == 'M' & df$id > 15,]

# Select Rows by list of column Values
df[df$state %in% c('CA','AZ','PH'),]

# Using is.element()
df[is.element(df$state, c('CA','AZ','PH')),]

# Using subset
subset(df, state %in% c("CA", "AZ", "PH"))

# Using dplyr::filter
dplyr::filter(df, state %in% c("CA", "AZ", "PH"))

# Using data.table
library(data.table)
setDT(df, key = 'state')[J(c("CA", "AZ", "PH"))]
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

###### merge two dataframes by a common column
```{r}
left_join(x, y, by = join_by(df1ColName == df2ColName))

#example
compoundlist_gen <- left_join(compoundlist_gen, siri, by = join_by(id == id))
#keeps all rows from df1, drops rows from df2 that don't have a match
```

###### Save as .csv
```{r}
write.csv(agg_all,"agg_all.csv")
write.csv(agg_parent_norm_all, "agg_parent_norm_all.csv")
```

###### Export figure as high res tiff for publication
```{r}
ggsave(
  "Raker_fig5.tiff",
  plot = last_plot(),
  device = "tiff",
  path = NULL,
  scale = 1,
  width = 150,
  height = 85,
  units = c("mm"),
  dpi = 300,
  limitsize = TRUE,
  bg = NULL
)
```
