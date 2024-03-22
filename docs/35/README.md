# Unweighted arithmetic average clustering

#clustering #method

Also called **Unweighted Pair-Group Method using Arithmetic averages (UPGMA)** or simply **average method**. 
It is based on the average distance between objects of difference clusters.

**Computation**

Compute the arithmetic average of the distances between an object and a cluster, or between two clusters, and fuse if below the current partion level.

$$d(u, v) = \sum_{ji} \frac{d(u_{i}, u_{j})}{|u| * |j|}$$

At each step, the objects or groups with the lowest pairwaise distance are fused, and the distance matrix is updated by averaging the distance of the fused objects/groups with the rest of the matrix (see Legendre and Legendre (2012) table 8.3 p.354 [^ref1])

**Consideration**
- All objects receive equel weights in the computation.
- Therefore, larger cluster have more influence on the calculation.
- **Because of the unweighted procedure, it assumes that all objects represent equaly the reference popultion under study**

[^ref1]: Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier.

