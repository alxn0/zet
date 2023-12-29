# Cophenetic distances and correlation

## Distance
In clustering, the cophenetic distance is the *distance treshold* at which two objects while be fused in a same cluster. 
In a [dendrogram](../18), it is the height (if the lengths of the branch are representative of the distance) at which objects/clusters are merged.

[dendrogram](./dendrogram.png)

In this example, the cophenetic distance between 212 and 214 is $\approx$ 0.4, while 432 and 431 $\approx$ 0.5. 

A cophenetic matrix is a $n$ by $n$ square matrix where the elements represent the cophenetic distance between the objects.

[matrix](./matrix.png)

## Correlation
### Definition
The Pearson correlation between original distance and cophenetic
distances. Can be used to assess the validity of the dendrogram.

Consider that:
- $x(i, j)$ is the original distance between objects $i$ and $j$
- $t(i, j)$ is the cophenetic distance between the same objects
- $\bar{x}$ is is the average of $x(i, j)$
- $\bar{t}$ is the average of $t(i, j)$

The cophenetic correlation between these distances (excluding the
diagonal) is:

$$ c = \frac{\sum_{i\<j} (x(i,j) - \bar{x})}{x} $$

$$ c = \frac{\sum_{i\<j} (x(i,j) - \bar{x}) (t(i,j) - \bar{t})}{\sqrt{\sum_{i\<j}(x(i,j)-\bar{x})^2 \sum_{i\<j}(t(i,j)-\bar{t})^2}} $$

### Interpretation
Cophenetic correlations range in -1 and +1, and it is expected to be positive if we compare distances (original and cophenetic), and negative if we compare distances with similarities. A value of 1 means a perfect correspondance between original ressemblance and cophenetic distances, and 0s means no correspondance at all.

### Sheppard-like diagram
Sheppard diagrams are scatterplot comparing two set of distances for the
same objects[^ref1]. They are used to compare distances in a reduced space
with distances in the original spaces. Departure from the diagonal indicate distortion in reduced space. 
In clustering analysis, they can be used to compare original and
cophenetic distances. In this context, we called them sheppard-like diagram.

### Relation to the mantel test
This matrix correlation is an application of the *standardized mantel test*, which can also be useful to:
	- compare two distance/similarity matrix of the same type of data
	- compare the  results of two clustering methods
	- Compares original distance and distances in a reduced dimension.
See p.412 of Legendre and Legendre (2014)[^ref2]

### Consideration
 We can use non metric correlation (e.g., Kendall's tau or Spearman's rho) if we are interested in the geometric structure of the dendrogram instead of the actual length of the branch.
- A cophenetic correlation cannot be tested for significance as cophenetic distances are not independant from the original ressemblance.
- Alternatively, the comparison of the same clustering applied to *different data sets* about the same objects can be statisticaly compared in terms of significance.

[^ref1]: They were first introduced by Shepard in is [paper](https://link.springer.com/article/10.1007/BF02289621) presenting non Metric Multidimensional Scaling. 
[^ref2]: Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier.


