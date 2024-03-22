# Silhouette coefficient

## Idea

The silhouette coefficient is used to assess the extent that clustering procedure produced *better* defined cluster[^ref3].

## Computation

The silhouette coefficient for a single object is:

$$ s = \frac{b - a}{\max(a, b)} $$

where $a$ is the the mean distance between a sample and all other points in the same class, and $b$ is the mean distance between a sample and all other points in the *next nearest cluster*, a.k.a. the *neighbour cluster*.

This statistic range in \[-1, 1\], where positive values means better belonging to its own cluster, and negative values is a point closer to neighbor cluster.

Can also be **average by cluster**, providing a fit values for each ones, or
**average for all objects**, providing a general clustering fit values.

## Interpretation

- **Higher values indicates better fits**
- **Negative values indicates points that are closest to another
  cluster than their own**

## Consideration

**PROS**:
- Allows to evaluation of each single object; help to identify potentiel outliers
- Work with any distance matrix.

**CONS**:
- Bias toward clustering that produce well separated cluster, and not chain-like cluster

## Implementation

- **Python**: `sklearn.metrics.silhouette_score`[^ref1]
- **R**: `cluster::silhouette`[^ref2]

[^ref1]: [https://scikit-learn.org/stable/modules/generated/sklearn.metrics.silhouette_score.html](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.silhouette_score.html)
[^ref2]:
    [https://www.rdocumentation.org/packages/cluster/versions/2.1.6/topics/silhouette](https://www.rdocumentation.org/packages/cluster/versions/2.1.6/topics/silhouette)
[^ref3]: Rousseeuw, P. J. (1987). Silhouettes: A graphical aid to the interpretation and validation of cluster analysis. Journal of Computational and Applied Mathematics, 20, 53–65. [https://doi.org/10.1016/0377-0427(87)90125-7](https://doi.org/10.1016/0377-0427\(87\)90125-7)

