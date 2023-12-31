# Calinski Harabasz index

## Idea

The calinski and Harabasz index (1974)[^ref1] as first developped to find the ideal partitioning of objects in K cluster. 
It is based on the general intuition that "optimal" clustering 
should maximum "cohesive clusters that are well separated from each others. It is a special application 
of $\frac{separation}{cohesion}$. It is also called **variance ratio criteria** as it is based on *sums of squared distance*. 
Therefore, cluster that are more compact and well separated will result in a better score.

## In Euclidean space

In euclidean space, the index is calculated as:

$$ ch = \frac{trace(S_B)}{trace(S_W)} * \frac{n-k}{k - 1} $$

where $S_B$ is the between-cluster scatterplot (or dispersion matrix) and $S_W$ is the within cluster scatterplot (or dispersion matrix). 
The trace of these matrice is the sum of its diagonal elements, which represents the sum of between and within clusters variance.

In geometric terms, it can be seen as the ratio between of the distances between the clusters centroids to the global centroid, 
over the distances between objects and their group centroid[^ref2]

## Arbitrary distances
**When using other distance measures**, the $ch$ index can be computed using the more general version of between-groups and within-groups sum of squares:

$$ ch = \frac{B(k)}  {W(k)} * \frac{n-k}{k-1} $$

Where

$$ B(k) = \frac{1}{n} \sum_{i, j = 1}^{n} d(x_i, x_j)^2 - W(k) $$

and

$$ W(k) = \sum_{h = 1}^{k}\ \frac{1}{|C_h|} \sum_{x_i, x_j \in C_h} d(x_i, x_j)^2 $$

In simple terms, $W(k)$ is the average of the sum of the square distances between objects in same groups. On the other hand, $B(k)$ is the sum of square distances between all objects in different clusters, calculated here as the sum of squares between all objects minum the sum of square distances between objects of same clusters (i.e., $W(k)$).

## Adjustment

Note that $B(k)$ is divided by $k-1$ and $W(k)$ is divided by $n-k$ to adjust for the effect of the number of clusters on the index value.

Explanation from chatGPT (unverified):

> The basic idea behind this adjustment is that adding more clusters to a clustering solution can increase the between-cluster 
> dispersion and decrease the within-cluster dispersion, regardless of the actual separation between the clusters. Therefore, a 
> clustering solution with more clusters may appear to have a higher Calinski-Harabasz index than a solution with fewer clusters, 
> even if the separation between the clusters is not actually improved.

## Interpretation

**Lower values indicate better fits**

## Considerations

**PROS**:

- Easy to compute
- Easy to interpret; based on an intuitive comprehesion of clusters
- General, can be computed with any distance matrix and parition vector

**CONS**:
- Sensitive to the shape and size of clusterl; does not perform well with irregular/complex cluster. Favor compacted and well separated cluster.
- Affected by the size of the dataset, should not be used to compare different clustering on different datasets
- Somewhat sensitive to outliers; outliers can affect between-cluster distances. Yet, outliser should be more of a concern when choosing distance measure and clustering algorithm.
- **A good value does not imply a best information retrieval**

[^ref1]: Caliński, T., & Harabasz, J. (1974). A dendrite method for cluster analysis. Communications in Statistics-Theory and Methods, 3(1), 1–27. https://doi.org/10.1080/03610927408827101
[^ref2]: [https://www.geeksforgeeks.org/calinski-harabasz-index-cluster-validity-indices-set-3/](https://www.geeksforgeeks.org/calinski-harabasz-index-cluster-validity-indices-set-3/)
