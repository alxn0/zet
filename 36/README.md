# Weighted arithmetic average clustering

lso called Weighted **Pair-Group Method using Arithmetic averages (WPGMA)**. It used a similar procedure than [UPGMA](../35), but gives equal weights to the two clusters (or object and cluster) that are about to fuse. In other words, it **downweight the distances in the largest group**.

**Computation**

The distance between objects is defined as:	$$ d(u, v) = (dist(s, v) + dist(t, v))/2$$ 
where cluster $u$ is form from the fusion of $s$ and $t$ and v is another cluster.

As for the [unweighted version](../35), the distance matrix is updated at each step with the 
weighted arithmetic distance for the fused objects/groups.

**Consideration**

- Give more contrasted groups than [unweighted arithmetic average
  clustering](../35)
- Good when we assume that the sample does not reflect the original study population
