# __PLS-DA Base Code__
#### Author: Cassie Raker
#### Last updated: November 17, 2022

#### Data uploaded and analyzed in R Studio

##### Code modified from Dr. Kevin Wong




```{r}
#select treatment names
Y <- agg_parent_norm_all$ATTRIBUTE_acclimation
```

```{r}
#select only data columns
X <- agg_parent_norm_all[5:58]
```

```{r}
#PLSDA without variable selection
MyResult.plsda <- mixOmics::plsda(X,Y) # 1 Run the method
plotIndiv(MyResult.plsda)    # 2 Plot the samples
plotVar(MyResult.plsda, cutoff = 0.5)
```

```{r}
plotIndiv(MyResult.plsda, ind.names = FALSE, legend=TRUE,ellipse = TRUE,title="PLS-DA")
```





























.
