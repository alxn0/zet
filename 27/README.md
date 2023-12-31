# Relative criteria for clustering internal validation

In comparison with [internal](../10) and [external](../20) validity, relative criteria does not rely on statistical testing. 
The fundamental idea of this approach is to choose the best clustering scheme of a set of defined schemes according to a pre-specified criterion.

**When looking the the best number of cluster, the problem can be stated
as**:

> *"Let $P_{alg}$ the set of parameters associated with a specific clustering algorithm (e.g. the number of clusters nc). 
> Among the clustering schemes Ci ,i= 1, ..., nc, defined by a specific algorithm, for different values of the 
> parameters in $P_{alg}$, choose the one that best fits the data set.”*[^ref1]

**There is two specific cases when searching for best $nc$:

1. **$P_{alg}$ does not contains $nc$ (i.e., number of clusters).** Run the algorithm for a wide range of parameters' values and choose the largest range for which $nc$ remain constant. Take the middle of this range.
2. **$P_{alg}$ contains $nc$**
	- Run the algorithm for all nc between a minimum $nc_{min}$ and a maximum $nc_{max}$
	- For each nc, run the algorithm r times (if there is a difference for each run) with different initial conditions
	- Plot the best value of the index $q$ (i.e., cluster statistic) by each $nc$
	- Look of a *knee* in the plot

**When comparing multiple clustering algorithm**

We must choose validation index that are not (too much) bias towards
certain clustering patterns (.e.g, hyperspherical around centroids).
Yet, not sure what is the best approach...

**Multiple statistics approach**

Hennig (2014)[^ref2] argue that relative criteria should be done with
multiple statistics that reflect different aspects of the
solutions. What he used is a mix of:

- Statistics that reflect the **connectedness** and the **separation** of the partitions, methods such as the [Calinski Harabasz index](../24) or the [Davies Bouldin Index](../25).
- **Stability index** assess how partition remains "stable" after the removal/randomization of input data like the Bootstrapped validation index
- Assess to what extent adding cluster **informe** on the original
  distance matrix, like the [Hubert's gamma index](../22) compared with
  a {1, 0} matrix.

[^ref1]: Halkidi, M., Batistakis, Y., & Vazirgiannis, M. (2001). On clustering validation techniques. Journal of Intelligent Information Systems, 17(2–3), [107–145. https://doi.org/10.1023/A:1012801612483]([107–145. https://doi.org/10.1023/A:1012801612483) p.23
[^ref2]: Hennig, C. (2014). How many bee species? A case study in determining the number of clusters. In M. Spiliopoulou, L. Schmidt-Thieme, & R. Janning (Eds.), Data analysis, machine learning and knowledge discovery (pp. 41–49). Springer.

