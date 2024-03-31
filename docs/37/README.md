# Unweighted centroid clustering

Also called Unweighted **Pair-Group Centroid Method (UPGMC)** or the **centroid method**. 
It is based on the distance between the centroid of the clusters (i.e., mean point).

**Computation**

The distance for fusion is defined as

$$ dist(s, t) = ||c_{s} - c_{t}||_{2} $$ 

where $s$ and $t$ are clusters, and $c_{s}$ and $c_{t}$ are their centroid. 
At each step, the distance matrix is updated with the centroid of the newly formed groups.

**Consideration**
- Can lead to reversal, which makes the dendrogram more difficult to interpret.
- Same assumption that in UPGMA, results can be extrapolated to a larger reference population.
- Tends to produce hyperspherical clusters (i.e., spherical in multidimensional space).
- If the observations are equaly distributed in multidimensional space, it tends to assign roughly the same number of objects in each group.
