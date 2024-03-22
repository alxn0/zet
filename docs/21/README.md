# Simple and adjusted Rand indices

Used to compare different *partitions* of the same object. 
It simply consider all pairs of objects and determine for each 
pairs whether they are placed or not in the same group.

## Simple Rand

We create a 2x2 contigency matrix which compares objects partitioning from 2 data clustering procedure.

![rand_contingency](./rand-contingency.svg)

- **$a$**: the number of pairs of objects that are in the **same** groups in partition 1 and 2.
- **$b$**: the number of pairs of objects that are in the **different** groups in partition 1 and in **same** group in partition 2.
- **$c$**: the number of pairs of objects that are in the **same** groups in partition 1 and in **different** group in partition 2.
- **$d$**: the number of pairs of objects that are in the **different** groups in partition 1 and 2.

From this, we calculate a simple *simple matching coefficient*[^ref1]

$$ Rand = \frac{a + d}{a + b + c + d} $$

which is the number of pairwise objects parition similarly divided by the total number of pairs. 
This give the proportions of similar partitioning between the two solution.

## Adjusted Rand

Corrected-for-chance version, the relationships between the two partitions is compare to that of a 
partitions picked at random, i.e., a random model. Different random models can be used depending on the partition algorithm.

See this [post](https://davetang.org/muse/2017/09/21/adjusted-rand-index/) for a detailed explanation of the adjusted rand index.

[^ref1]: Legendre, P., & Legendre, L. (2012). Numerical ecology (3rd ed., Vol. 24). Elsevier. Eqution 7.1., p.274

