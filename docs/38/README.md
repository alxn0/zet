# Weighted centroid clustering

Also called **Weighted Pair-Group Centroid Method** (WPGMC) or **median** method. 
As with the [centroid](../37) methods, but gives equal weights to the two clusters (or object and cluster).

**Computation**
See Legendre and Legendre (2012) p.360

**Considerations**
- The weighting control for the underrepresentation of certain types of objects that were not as well-sampled as in [weighted arithmetic average clustering](../36).
- Tends to produce hyperspherical clusters (i.e., spherical in multidimensional space).
- If the observations are equaly distributed in multidimensional space, it tends to assign roughly the same number of objects in each group.

## References
Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier.

