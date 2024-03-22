# Clustering with semimetric distances

#clustering #space

From a discussion on [hierarchical agglomerative methods](../32) on cross
validated:

> [Single, complete](../28) and [average](../34) methods need only positive and
> symmetric coefficient (i.e., semimetric). [Ward](../39), [centroid](../34) and *median*
> methods need squared euclidean distances to produce geometricly
> meaningful results.[^ref1]

Same observation with **k-mean** which expect quared Euclidean distances. 

Alternatively, **k-medoids** relies on data points for *centers*, yet it look to actual
data points for medoids, and minimize distance from these real
observations. Therefor, they can work with arbitrary distance measures,
and are more suited to k-means. They try to identify the *nearest
medoids*. Still, partitioning around medoid can produce suboptimal solutions when
triangle inequality does not hold.

My understanding is that calculating centroid within cluster 
need metric distance to make sense. In other words, centroids are 
not meaningful summaries of the cluster. By extension, 
mean error squares within cluster may not be as reliable in
non metric space. 

More generally, without triangle inequalities, cluster may not 
be coherent regions and the notions of **compactness** and 
**separation** may not aling with the behaviors of distance measure.

Alternatively, algorithms based on **nearest neighbors** such has some 
hierarchical (e.g., single linkage) or density-based algorithms (e.g., DBSCAN) 

Another approach is to relies on **graph-based** approach (e.g., spectral
clustering), were similarities are analyzed as graphs. Graphs can 
handle semimetric similarities, but also non-metric ones. 

A last workaround is to **transform or scale** non-metric distances into
metric ones before applying clustering algorithm.

---

Some other methods especially suited for semimetric distance:

- [relational k-means](https://arxiv.org/abs/1304.6899)
- [relational
  fuzzy-c](https://www.sciencedirect.com/science/article/pii/S0888613X08001412)
- [affinity
  propagation](https://www.science.org/doi/abs/10.1126/science.1136800)

Here some ineteresting references on clustering with non-metric
distances

- [Ackermann and al.,
  (2010)](https://dl.acm.org/doi/abs/10.1145/1824777.1824779)
- [Kuman and al., (2014)](https://infocomp.dcc.ufla.br/index.php/INFOCOMP/article/view/21)

[^ref1]: <https://stats.stackexchange.com/questions/13873/does-a-distance-have-to-be-a-metric-for-an-hierarchical-clustering-to-be-valid>
