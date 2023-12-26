# Similarity and distance

Similarities are measures of *likeness* between
objects. Takes the maximum values if objects are identical, and 0s if
entirely differents. 

Inversely, distances are measure of *separation* between objects. 
Values are maximized if objects are completely different, while
identical object are at a distance of 0.[^Dissimilarities]

When having normalized coefficients that range in $[0, 1]$, we can get
corresponding coefficients.[^Equation]

$$D = 1 - S, \quad D = \sqrt(1 - S), \quad D = \sqrt(1 - S^2)$$

See Section 7.3 and 7.4 in Legender and Legender (2012)[^Legendre] for an
exhaustive review of coefficients.

[^Legendre]: Legendre, P., & Legendre, L. (2012). Numerical
ecology. Elsevier. 

[^Dissimilarities]: *Distance* and *Dissimilarities* are often used interchangeably,
although they can mean different [things](../4).

[^Equation]: Or inversely from D to S

