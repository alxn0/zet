# Traditional clustering algorithms

Here's a quick categorial overview of some of the mostly used *traditional* clustering
methods.

Most of this information is taken from Xu and Tian (2015)[^ref1] and
Ezugwu and al. (2022)[^ref2] 

1. **Hierarchical-based clustering**

- *Example*: Single-, complete- and average-linkage
- *Logic*: Builds clusters based on distance between objects.  Clusters
  are merged or split based on minimal/maximal
  distances between objects, or between cluster centroids, depending on
  the algorithms. Results in a dendrogram representing nested clusters
  at different distance levels.
- *Advantages*: Easy to implement and to interpret, allows to explore hierarchical
  clustering structure, can be used with arbitrary distances (therefore
  arbitrary type).
- *Limitations*: High computational cost in general (limit used with big data), wrong *connection* can't be
  undone, need a cutpoint in the dendrogram for k cluster.

> All the following methods are partitionnal-based methods, meaning that they
produce a single partition of the data, in contrast with previous
hierarchical-based methods

2. **Centroid-based clustering**

- *Example*: K-means and k-medoids
- *Logic*: Represent each cluster according to a central vector
  (centroid). Centroid are move iteratively, and optimization is done
  on the square error distance to these centroids. Works well when
  cluster are compact and spherical. Based on euclidean distances for
  k-means, and arbitrary distances for k-medoids.
- *Advantages*: Low computational cost and easy to implement.
- *Limitations*: Need to specify a priori number of cluster, biases towards
  spherical clusters, sensible to noise (although k-medoids is more
  robust), sensitive to the number of clusters, easily drawn in to local
  optimal (workaround → multiple iterations)

3. **Density-based clustering**

- *Example* : DBSCAN
- *Logic*: Based on the objects space, conncect areas of high density
  into clusters. Allows for more arbitrary-shaped such as elongated dense
  or doghnut-like areas.
- *Advantages*: Non-biased toward specific shape. Robust to outliers
- *Limitations*: Need to select appropirate parameters. Difficulties with
varying density and high-dimensionnal data.

> Methods 4 and 5 both involve a statistical framework which involve the
> estimation and optimization of parameters.

4. **Distribution-based clustering**

- *Example*: Gaussian mixture model
- *Logic*: Assume the data is generated from
  a combination of probability distributions. The clustering process
  involves identifying these distributions (i.e., their parameters) and
  assiging objects to the most likely distribution. Distances from the
  distribution center define likelihood of belongings to a cluster.
- *Advantages*: More realistic to consider probability of belonging to
  a cluster (soft cluster). Hability to represent cluster of different size.
  Easy to implement.
- *Limitations*: Initial paramaters strongly influence the
  clustering results. Should not be used when having no clue on the data
  type of distribution.

5. **Model-based clustering**
- *Example*: COBWEB
- *Logic*: Takes a more general approach to the previous
  distribution-based methods by fitting the data to a model that is not
  defined strictly in terms of probability distribution, such as
  statistical learning and neural networks.
- *Limitations*: More complex models allows a greater flexibility than
  distribution-based models. Clusters can be described by the underlying
  model. Can bring significant advantages is specific domains.
- *Disadvantages*: Relatively high time complexity. Difficulties in selecting the right models and the
  potential of overfitting. Clustering sensitive to parameters.

6. **Fuzzy-based clustering**
- *Example*: Fuzzy c-means
- *Logic*: Cluster are defined as fuzzy sets in which objects
  simultaneaously belongs to multiple clusters. The discrete belongin to
  cluster {0, 1} is changed to a continuous interval [0, 1]. Objects are assigned to
  clusters with various level of membership, implying overlapping
  clusters. 
- *Advantages*: More realistic to have different degree of belongin to
  cluster.
- *Disadvantages*: Local optimal, sensitive to initial parameters value,
  number of cluster need to be preset.

[^ref1]: Xu, D., & Tian, Y. (2015). A comprehensive survey of clustering algorithms. Annals of Data Science, 2, 165–193. [https://doi.org/10.1007/s40745-015-0040-1](https://doi.org/10.1007/s40745-015-0040-1)
[^ref2]: Ezugwu, A. E., Ikotun, A. M., Oyelade, O. O., Abualigah, L., Agushaka, J. O., Eke, C. I., & Akinyelu, A. A. (2022). A comprehensive survey of clustering algorithms: State-of-the-art machine learning applications, taxonomy, challenges, and future research prospects. Engineering Applications of Artificial Intelligence, 110, 104743. https://doi.org/10.1016/j.engappai.2022.104743


