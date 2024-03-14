# __PLS-DA Base Code__
#### Author: Cassie Raker
#### Last updated: March 13, 2024

#### Data uploaded and analyzed in R Studio

##### Code modified from Dr. Kevin Wong and various mixOmics forums




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
plotIndiv(MyResult.plsda, ind.names = FALSE, legend=TRUE, ellipse = TRUE, title="PLS-DA")
```

It's actually all ggplot2 under the hood, so you can extract the golly object and customize like this:
```{r}
dp_acc <- plotIndiv(MyResult.plsda, ind.names = FALSE, legend=TRUE, ellipse = TRUE, title="Direct Parent PLS-DA: Acclimation")$graph
dp_acc <- dp_acc + scale_color_manual(name = "Days in \nAcclimation \nCage", labels=c('126 Days', '112 Days', '38 Days', '24 Days', '0 Days'), values=c("#3f8cd1", "#f28d0a", "#c2c2c2", "#249e6e", "#c979aa"))
dp_acc
```

I've liked export dimensions 750x500



























.
