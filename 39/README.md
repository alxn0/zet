# Ward's minimum variance clustering

As for the centroid methods (i.e., [unweighted](../37) and [weighted](../38) centroid clustering), it also leads to a gemetric representation where centroïds are important. Minimize an objective functions wich is the square error as in multivariate analysis of variance.

**Computation**

At the begining, each object is in its own cluster, with distances between objects and the centroid of their respective cluster equal 0. As objects fuse into clusters, the centroid move away from objects and the square distance from object to centroid increase. The ward algorithm minimize these distances.

The sum of squared distances of all objects to their common centroid is the equivalent of *error* in ANOVA, which is the squared Euclidean distances between cluster's members and their centroid. Error in a cluster k is defined as:
$$e_{k}^2 = \sum_{i = 1}^{n_k} \sum_{j = 1}^{p} [y_{ij}^k - m_{j}^{k}]^2$$

where $y_{ij}^k$ is the value of descriptor $y\_j$  for an object $i$ member of group $k$ and $m_j^k$  is the mean value of descriptor $j$ over all members of group $k$ .  The squared error $e_k^2$ is used as a measure of the *tightness* of a cluster.

Consequently, the ward algorithm tries to minimize the following criterion:
$$ E_k^2 = \sum_{k = 1}^K e_k^2 $$
where $E_k^2$ is the sum of squared errors over all $K$ clusters. In ANOVA terminology, the ward algorithm minimize the total *within-group sum-of-squares*.

**Consideration**

- Tends to produce hyperspherical clusters (i.e., spherical in multidimensional space).
- If the observations are equaly distributed in multidimensional space, it tends to assign roughly the same number of objects in each group.
- The ward's algorithm is a hierarchical algorithm that tries to minimize the delta of $E_k^2$ at each step. Therefore, it does not guarantee that the solutions for each number of clusters provides tha best solutions in terms of minimizing the sum of squared errors. To obtain an optimal solution of a given number of clusters, an alternative is the [[k_means_partitioning|K-means]] algorithm
- Dendrogram can be represented along different scales such as the *squared distances* or the *sum of squared errors*. Another option is the square roots of the fusion distances, which remove the distortion created by the squaring distances. It is used in `agnes()` in R and is suitable to compare Ward's distance with original ones (see [[sheppard_diagram|Shepard-like diagram]] and [[cophenetic_distance|cophenetic]] correlations).
