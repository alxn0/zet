# Minkowski distance

Minkowski's metric is a generalization of the Euclidean and Manhattan distances. It is defined as:

$$ D(x, y) = \left( \sum_{i=1}^{n} |x_i - y_i|^p \right)^{1/p} $$

where $x$ and $y$ are two vectors in the $n$-dimensional space, and $p$ is a parameter that defines the metric. When $p=1$, the Minkowski distance is equivalent to the Manhattan distance, and when $p=2$, it is equivalent to the Euclidean distance.

For power $p > 1$, the Minkowski distance is a [metric](../16/README.md), while for $p < 1$ it is not as it violates the triangle equalities.

For $p > 2$ it gives more weight to large differences between values, while for $p < 2$ it gives more weight to small differences. 

## References

<https://en.wikipedia.org/wiki/Minkowski_distance)>
Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier. Equation 7.43.

