# Hubert' gamma statistic


The main objective behind the original definition the the Hubert's $\Gamma$ statistic[^ref1] is to assess the power of a certain 
cluestering against certain types of alternatives hypothesis. Generally, the alternative hypothesis is a null hypothesis 
where partition are distributed at random into partitions.

##  Null hypothesis

One option is that the $n(n-1)/2$ ressemblance values have been assigned at random to the object pairs. If randomness cannot be rejected, 
the hierarchy yielded by the clustering procedure will be considered an artifact of the method rather than the result of any structure inherent in the data.

To test such hypothesis, we need to find some statistic $G$ that is a function of the partition which will be used to compare the dissimilarities with 
the resulting clustering, either empirical or from the null hypothesis (permutation / monte carlo simulation).

In the case of hierarchical clustering, they argue that testing the power of a given partition against an alternative hypothesis is more relevant 
than testing the whole partition structure (i.e., the partition tree).

## Calculation

The general idea is to measure the correlation between two ressamblance matrix of the same shape:

$$ \Gamma = \frac{1}{m} \sum_{i = 1}^{n - 1} \sum_{j = i+1}^{n} X(i,j)Y(i,j) $$

where $m$ is the total number of possible pairs in X (or Y), being $m = n(n-1)/2$.

There is a normalized (or adjusted) version:

$$ \hat{\Gamma} = \frac{1}{m} \sum_{i = 1}^{n - 1} \sum_{j = i+1}^{n} (X(i,j) - \mu_X)(Y(i,j)-\mu_Y)\ /\ \sigma_X \sigma_Y $$

where $\mu_X, \mu_Y, \sigma_X$ and $\sigma_Y$ are the means and variance of X and Y. It is the Pearson's correlation coefficient between the elements of X and Y.

In this framework, we can compare different [[ressemblance]] matrix and/or clustering results by defining:

$$ Y_{binary} = \begin{cases} 1\ if\ i\ and\ j\ belongs\ to\ different\ clusters \\ 0,\ if\ i\ and\ j\ are\ in\ the\ same\ cluster
\end{cases} $$


## Usage

**External validity**:
- This can be applied to compare the clustering result $C$ with an external solution $P$. First we create two binary matrices, which correpond to the objects being in the same groups (1) or different (0).
- It can also be used to compare the original ressemblance matrix ($S$ or $D$) with a binary matric of an external solution $P$.

**Internal validity**
- Validate a given clustering at K cluster by comparing the ressamblance matrix with a binary matrix such as $Y_{binary}$.

**Relative validity**
- Compare the compactness of different solutions, by calculating $\Gamma$ (or $\hat{\Gamma}$ ) on the ressamblance matrix and a matrix which provides the distances between the representative points of the cluster of $i$ and $j$. Here representative points can be for example the centroid (for metric distance) or medoid. This is often called the **modified Hubert's $\Gamma$ (or $\hat{\Gamma}$) statistic**.

## Readings

Good explanation in chapter 16 of Theodoridis (2008)[^ref2]

[^ref1]: Hubert, L. (1972). Some extensions of Johnson’s hierarchical clustering algorithms. Psychometrika, 37(3), 261–274. [https://doi.org/10.1007/BF02306783](https://doi.org/10.1007/BF02306783)
[^ref2]: Theodoridis S., K. K. (2008). Pattern recognition (4ed ed.). AP. libgen.li/file.php?md5=8c5dc6881aab989aa927d0eaaeb84c0c

