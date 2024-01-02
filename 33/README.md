# Representations of hierarchical clustering solutions

**Dendrogram**

A [dendrogram](../18) is a common way to represent hierarchical clustering results. Dendrograms will display the different step at which objects/groups are fused based. For conveniance, the length of the branch will ofently represent the partition level (i.e., the measure treshold) at which fusion happened, with perpendicual lines connecting the two branches.

![clustering\_dendrogram](clustering_dendrogram.png)
*Illustration of a single linkage dendrogram found in Legendre and Legendre (2012) p. 344, Figure 8.2* [^ref1].

**Subgraphs**

Another options is to visualize connected subgraphs at each partition level.

![subgraphs](subgraphs.png)

*Illustration of a subgraphs representation of the same single linkage clustering (see Legendre and Legendre (2012) p.344, Figure 8.2* [^ref1]*). 
New links are displayed in bold.*

**Cophenetic matrix**

astly, any classification can be fully described by a [cophenetic matrix](../23), where each element of the matrix, namely the [cophenetic distances](../23), are the distance at which each pairs of objects become part of the same group.

![cophenetic](cophenetic.png)

*Cophenetic matrix of the previous single linkage partitioning. See
Legendre and Legendre (2012) p.346* [^ref1]

[^ref1]: Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier.

