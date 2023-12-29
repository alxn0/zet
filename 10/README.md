# Clustering validity based on internal criteria

The idea is to evaluate the clustering solution on properties injerent to the data sets. 
There is no *external* information used. It can be used to assessed the best
clustering algorithm and the optimal number of cluster, but also find
and evaluate the effect of removing outliers.

Considering the the *goal* of clustering is to assign similar objects
within same cluster, and dissimilar objects in different
ones. 

Therefore, internal validation ofthen relies on the following
criteria:

- **Compactness**: How *closely related* are objects within same clusters
- **Separation**: How well-separated are different clusters.

> A *good* clustering solution is expected to have *compact* cluster
> that are *well-separated* from each others.

Here are some coefficients that I used to evaluate a single clustering
scheme:

- **Calinski-Harabasz index**: Based on the average between-
  (separation) and within-cluster (compactness) sum of squares.
- **Silhouette index**: Calculate for each object the ratio between 
  the mean distance o all other object of its cluster, and the minimum distance 
  with the closest cluster. Can be used to assess how object belong 
  to their own cluster.
- **Davies-Bouldin index**: Use the average similarities between
  clusters, were similarities are the ration of within- and between
  cluster distances.
- [**Hubert Γ statistics**](../22): Evalute the difference between clustering
  solutions by counting disagreements between partitions. Can be used to
  evaluate a *single clustering scheme* either by comparing to a {0, 1}
  matrix, or one simulated from a monte carlo procedure to test the
  random hypothesis of a given data set.


Xiong and Li (2014)[^ref1] compared 12 internal measures on the impact of
monotonicity, noise[^info1], uneven density and
subclusters[^info2], skewer distributions[^info3] and arbitratry shapes.

- **Calinski-Harabasz** could not handle  noise, skewed distribution
  and arbitrary shapes.
- **Average Silhouette** and **Davies-Bouldin** could not handle subclusters and
  arbitrary shape.
- **Cluster Validation Indeb based on Nearest Neighbors (CVNN)** performed well in all six aspects.

When using a hierarchical clustering algorithm, the hierarchy can be
evaluated using the [**Cophenetic correlation coefficient**](../23). Can be used to test the
random hypothesis, but also observed how specific hierarchical algorithm
biais pairwise connections toward smaller or larger distances (see
Lengendre and Legendre (2012)[^ref2].

[^ref1]: Xiong, H., Li Z. (2014). Clustering Validation Measures. In Aggarwal, C. C. (ed.), Reddy C. K.. (2014). Data Clustering: Algorithms and Applications (First edition). Chapman and Hall/CRC.
[^ref2]: Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier.
[^info1]: Points that are in between clusters.
[^info2]: Clusters that are close to each others,
[^info3]: Number of points in clusters. Test uneven cluster size
