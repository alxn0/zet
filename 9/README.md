# Clustering validation

Evaluate validity of a clustering solution is not an easy task, but an
important one considering that:

- Clustering algorithms will give rise to partition wether or not the uderlying data pertain to different cluster.
- Different algorithm will provide different results based on the uderlying assumption about cluster "shape"
- Different methods are variously sensitive to noise

Consquently clustering validity assessment will help answers the
following questions:
- Is the cluster are *real* of simply an artefact of the underlying algorithm?
- Is the cluster results best fits the underlying data?

Here are categories of **Validation measures**:
1. Internal criteria
2. External criteria
3. Relative criteria

Here are good references on clustering validation methods:
    - Halkidi and al., (2001)[^ref1] (Dated but well explained)
    - Xiong and Li (2014) (Extensive reviews with comparison analysis)
    - Hennig (2014)[^ref3] (Case study on finding bee species) 

[^ref1]: Halkidi, M., Batistakis, Y., & Vazirgiannis, M. (2001). On clustering validation techniques. Journal of Intelligent Information Systems, 17(2–3), [107–145. https://doi.org/10.1023/A:1012801612483](https://doi.org/10.1023/A:1012801612483)
[^ref2]: Xiong, H., Li Z. (2014). Clustering Validation Measures. In Aggarwal, C. C. (ed.), Reddy C. K.. (2014). Data Clustering: Algorithms and Applications (First edition). Chapman and Hall/CRC.
[^ref3]: Hennig, C. (2014). How many bee species? A case study in determining the number of clusters. In M. Spiliopoulou, L. Schmidt-Thieme, & R. Janning (Eds.), Data analysis, machine learning and knowledge discovery (pp. 41–49). Springer.

