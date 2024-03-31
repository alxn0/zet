# External criteria for clustering validation

Evaluate the results of a [clustering](../5) with a pre-specified structure which reflects our intuition about 
the clustering structure. Use to test the *Null Hypothesis* that the
dataset as a random clustering structure.

One approach with to assess clustering validity through [Monte Carlo
simulation](../0). We then compare the empirical partition with the ones
obtains from the simulated data unsing a *statistitic index*. Then we
checked the density distribution of this *index*, and reject $H_{0}$ if
the empirical $q$ is smaller (or greater) than $p$ proportion (normaly
5%) of $q simulated* values.

**Some method to compare partitions**:

- [Rand index](../21)
- [Mutual Information Score](../0)
- [Hubert's and the normalized $\gamma$ statistics](../22)
