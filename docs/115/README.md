# Manifold hypothesis 

## Manifold

 - A **manifold** is a topological space that locally resembles Euclidean space near each point.
 - A **topological space** is a set of points with a topology, which is a set
   of neighborhoods for each point. 
 - A **neighborhood** defined for each point in the space, is a set of points that are close to the point.
   Here closeness can be defined differently.

In other words, a topological space is a geometrical space in which closeness is
defined, but cannot necessarily be measured by a [distances](../4/README.md) metric.

Therefore, a manifold is a space that is locally Euclidean, but globally can have a more complex structure.

## Manifold hypothesis 

The **manifold hypothesis** is a hypothesis that states that high-dimensional data
can be embedded into a lower-dimensional space, assuming that each feature of 
a data point do not carry an equal amount of information. In other words, the
*d*-dimensional data points lie on a *k*-dimensional Euclidean space, 
where *k* << *d*.

## Manifold learning
[**Manifold learning**](../114/README.md), or non-linear
dimensionality[^1]
reduction is a technique that allows to embed (i.e., embed objects from 
one space to another) high-dimensional data into lower-dimensional space assuming
there is a latent manifold structure in the data.

The **input space** refers to the high-dimensional space where the data points
are located, and the **output space** refers to the lower-dimensional space
where the data points are embedded. The output space is also
called the *subspace*, the *submanifold*, or the *embedding space*.

[^1]: Althoug manifold learning is usually used to describe
non linear dimensionality reduction techniques, it is sometime used to describe
linear dimensionality reduction techniques (see page 4 in Ghojogh and al., 2023).

## References

<https://en.wikipedia.org/wiki/Manifold>

Meilă, M., & Zhang, H. (2023). Manifold learning: What, how, and why.

Ghojogh, B., Crowley, M., Karray, F., & Ghodsi, A. (2023). Elements of dimensionality reduction and manifold learning. Springer Nature. 

