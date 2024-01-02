# What about metric distances and metric space?

For any distance coefficient, we consider it to be **metric** if it follows
the following properties:

- **minimum of 0**: if $a = b$, then $D(a, b) = 0$
- **positiveness**: if $a \neq b$, then $D(a, b) > 0$
- **symmetry**: $D(a, b) = D(b, a)$
- **triangle inequality**: $D(a, b) + D(b, c) \geq D(a, c)$[^info1]

Based on these four properties, we categorized distances (or
dissimilarities)[^info2] as:

1. **Metric**: satisfy the four metric properties
2. **Semimetric**: Violate the triangle inequalities
3. **Non metric**: Have negative values

Following this, we defind a *metric* as a set elements with given
pairwise *metric* distances. Formaly, it is an ordered pair $(M, d)$
where $M$ is a set of ojects and $d$ are the metric distances between
elements of $M$

*Metric space* is probably the most intuitive *space* to understand, as
it is the space of euclidean geometry. Most algorithm relying on
distances will either expect,  or work well, with metric distances.

Still, we need to verify if we are working with metric distances, and if
not, ensure that used algorithm for analyses are adapted for non metric
(or semimetric) distances.

For example, *k-mean* clustering is not adapted in semimetric/nonmetric space, as measuring centroids make less sense without the triangle inequality being respected. 

In chapter 7 of Legendre and Legendre (2012), Table 7.1 and 7.2 provides
the metric properties of an extensive list of distance and similarity
coefficients. 

Related notes:
- [Clustering analysis in semimetric space](../16)
- Dimensionnality reduction in semimetric space (**TODO**)

[^info1]: In Euclidean space, it means that two sides of a triangle is necessarily equal to or larger than the third side.
[^info2]: Sometimes, their is a distinction between distance and dissimilarities, the first being in metric space, while the second being more general categories that include metric and non metric dissimilarities. This distinction is not always made (explicitely) in the academic litterature.

