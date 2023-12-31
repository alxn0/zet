# Davies Boulding Index

## Idea

The Davies and Bouldin (1979)[^ref1] index can be used as an internal measure of cluster results. As for 
[Calinski Harabasz index](../24), it is based on the intuition of a *best* solution means 
compact cluster that are well-separated from each other.

However, it differs in its formulation as it is defined as the average similarity measure 
of each cluster with its most similar cluster, where similarity is the ratio of within-cluster 
distances to between-cluster distances. Thus, clusters which are farther apart and less dispersed will result in a better score.

## Computation

The general formulation is based on the average similarity between clusters and the distance between their centroids:

Consider that $R_ij$ is a similarity measure between clusters $i$ and $j$. It can be computed as

$$ R_{ij} = \frac{s_i + s_j}{d_{ij}} $$ 

Where $s_i$ and $s_j$ are the average distance between all points of clusters $i$  and $j$ and their centroids. 
Then, $d_{ij}$ is the distance between the centroids of clusters $i$ and $j$. 
Therefore, similar clusters (i.e., similars $s_i$ and $s_j$) which are close from other (i.e., small $d_{ij}$) will be highly similar.

From these, we can define the index as:
 
$$ db = \frac{1}{k} \sum_{i, j = 1}^{k} max_{i \neq j} R_{ij} $$

Which is simply average the sum of all maximum similarities for all cluster, namely the cluster that it most similar to a given cluster.

There is a nice blogpost on PyShark which detailed the
computation[^ref2]

## Interpretation

**Lower values means better fit**

## Considerations

**The Davies Bouldin only works for metric distance as it relies on
centroid**

## Implementation

- **Python**: `sklearn.metrics.davies_bouldin_score`[^ref3]
- **R**: `clv::clv.Davies.Bouldin`[^ref4]

[^ref1]: Davies, D. L., & Bouldin, D. W. (1979). A cluster separation measure. IEEE Transactions on Pattern Analysis and Machine Intelligence, PAMI-1(2), 224–227. https://doi.org/10.1109/TPAMI.1979.4766909
[^ref2]: [https://pyshark.com/davies-bouldin-index-for-k-means-clustering-evaluation-in-python/](https://pyshark.com/davies-bouldin-index-for-k-means-clustering-evaluation-in-python/)
[^ref3]: [https://scikit-learn.org/stable/modules/generated/sklearn.metrics.davies_bouldin_score.html](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.davies_bouldin_score.html)
[^ref4]: [https://search.r-project.org/CRAN/refmans/clv/html/Davies_Bouldin.html](https://search.r-project.org/CRAN/refmans/clv/html/Davies_Bouldin.html)
