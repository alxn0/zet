# non Metric multidimensional scaling

Metric multidimensional scaling (MDS) is a technique used to project high-dimensional data into a lower-dimensional space. It originated in the field of mathematical psychology, as a method of ordination for nonmetric variables (Sheppard 1980). The core algorithm originated in two papers by Sheppard (1962 a, b) and was later extended and optimized by Kruskal (1964 a, b).

## Sheppard Definition

The goal of nMDS is to find an appropriate spatial configuration of
undefined proximity measures between objects, as points in an Euclidean
space of lower dimensionality. "Appropriate" configurations here means
that distances between points in the original and the lower dimensional
spaces are monotonically related, i.e., the closer two points are in the
original space, the closer they should be in the lower dimensional space,
and vice versa.

The evident advantage of nMDS over MDS is that there is no assumptions
on the function used for proximity measures or their corresponding
distances; all it requires is that distances are monotonic.

The configurations is found through an iterative process that is
described in Shepard (1962b), but is not used anymore. Istead, we rely
on stress as a loss functions as described in Kruskal (1964a).

## Kruskal improvment: Stress optimization

A limit of Sheppard's algorithm is that it does not give a mathematical
definition of what is an "appropriate" configuration. To address this, 
Kruskal (1964a) introduced the concept of stress as a [loss
function](../108/README.md) to 
be minimized. Stress is a measure of the discrepancy between the
distances in the original and the lower dimensional spaces. The stress
function is defined as:

$$ S = \sqrt{\frac{\sum_{i, j} (d_{ij} - \hat{d}\_{ij})^2}{\sum_{i, j} d_{ij}^2}} $$

where $d_{ij}$ is the distance between points $i$ and $j$ in the original matrix
and $\delta_{ij}$ is the distance between the same points in the lower dimensional.

The differences between $d_{ij}$ and $\delta_{ij}$ are squared to avoid negative values. 
The denominator is used to normalize the stress value, so it can be compared across
different datasets.

A value of 0 indicates complete accordance between all rank order distances 
in the input data and the final ordination.

Although it can be calculated between 0 and 1, the maximum value for 2D
is 0.58, and this value decrease with increasing number of dimensions
(De Leeuw and Stoop 1984).

## Stress 2

An alternative to previous stress definition is to change the scaling
factor (i.e., denominator) as follows:

$$ S = \sqrt{\frac{\sum_{i, j} (d_{ij} - \hat{d}\_{ij})^2}{\sum_{i, j} (d_{ij} - \bar{d})^2}} $$

## Algorithm

### Detailed

1. Take an arbitrary dissimilarity matrix $D$ with $n$ objects
2. Specify the number of $m$ dimensions
3. Initialize a random configuration of $n$ points in an Euclidean space of *m* dimensions
4. Calculate the metrix of fitted distances $d$ between all points in the
   reduced spaces with one of [Minkowski's metrics](../110/README.md) (usualy the Euclidean
   distances).
5. Rank elements of the matrix $D$ and $d$ in ascending orders
6. Regress the ranks of $D$ on the ranks of $d$, usualy through
   a monotonic regression. Predicted values are the new distances
   $\hat{d}$
7. Calculate the stress function $S$ and compare it to a small predermined
   value $\epsilon$
8. Improve this configuration by moving the points in the Euclidean space
   in order to decrease stress. This is done by a gradient descent
   or other method.
9. Repeat step 4 to 8 until the stress is below a predetermined treshold
   $\epsilon$.
9. Optionnaly, nMDS may be rotated using PCA to improve interpretation

See Legendre and Legendre (2012; section 9.4) for a detailed description of the
algorithm.

### Compact

A more compact form of this algorithm is (Wikipedia) :
-  Initialize $x_i$ randomly, e. g. by sampling from a normal distribution. 
-  Do until a stopping criterion (for example, $S\epsilon$)
    - Solve for $f = argmin_f S(x_1, ..., x_n ; f)$ 
    - Solve for $x_1, ..., x_n = argmin_{x_1, ..., x_n}  S(x_1, ..., x_n ; f)$. 
- Return $x_i$ and $f$ 


## Interpretation of stress

A general rule of thumb to assess the quality of the ordination is that:

- $S < 0.05 $ provides an excellent representation
- $S < 0.1 $ is a good representation
- $S < 0.2 $ is a fair representation
- $S > 0.2 $ is a poor representation and should not be interpreted


Although stress is discuss as a goodness-of-fit measures, it does
not represent suh measure in a conventional sense, but more like
an AIC or BIC, as it is used to optimized the ordination.

Still most papers in ecology use stress to assess the quality of the
ordination, and no other approach (Dexter et al., 2018)

## Considerations

- nMDS axes are arbitrary, so the plot can be rotated, centered of
  inversed
- Sensible to initial configuration (step 3), avoid by running the
  programs *b* times.

## References

De Leeuw, J., and I. Stoop. 1984. Upper bounds for Kruskal’s stress. Psychometrika 49: 391–402. doi:10.1007/ BF02306028

Dexter, E., Rollwagen‐Bollens, G., & Bollens, S. M. (2018). The trouble with stress: A flexible method for the evaluation of nonmetric multidimensional scaling. Limnology and Oceanography: Methods, 16(7), 434–443. https://doi.org/10.1002/lom3.10257

Kruskal, J. B. 1964a. Multidimensional scaling by optimizing goodness of fit to a nonmetric hypothesis. Psychometrika 29: 1–27. doi:10.1007/BF02289565 

Kruskal, J. B. 1964b. Nonmetric multidimensional scaling: A numerical method. Psychometrika 29: 115–129. doi: 10.1007/BF02289694

Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier.

Shepard, R. 1980. Multidimensional-scaling, tree-fitting, and clustering. Science 210: 390–398. doi:10.1126/ science.210.4468.390

Shepard, R. N. 1962a. The analysis of proximities: Multidi- mensional scaling with an unknown distance function. I. Psychometrika 27: 125–140. doi:10.1007/BF02289630 

Shepard, R. N. 1962b. The analysis of proximities: Multidi- mensional scaling with an unknown distance function. II. Psychometrika 27: 219–246. doi:10.1007/BF02289621

Wikipedia. Nonmetric multidimensional scaling. https://en.wikipedia.org/wiki/Multidimensional_scaling
