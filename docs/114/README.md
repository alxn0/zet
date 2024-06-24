# Feature extraction dimensionality reduction classification

## Linear and non linear methods

 - **Linear methods**: The new features are linear combinations of the original features.
    - Case: PCA, Linear discriminant analysis, Factor Analysis

 - **Non-linear methods**: The new features are non-linear combinations of the original features.
    - **Global**: The new features are created by considering the data set global structure.
        - Case: Isomap, Multi-dimensional scaling
    - **Local**: The new features are created by considering the data set local structure.
        Produce better results when "the local geometry is close to
        Euclidean space", but "the global geometry is probably not"
        - Case: Locally-Linear-Embedding (LLE), t-Distributed Stochastic
          Neighbor Embedding (t-SNE)

## Supervised and unsupervised dimensionality reduction

 - **Supervised dimensionality reduction**: The new features are created with the
    help of labels (i.e., prior information on the objects). The
    goal is to create new features that are useful for the prediction
    task.
        - Case: Linear discriminant analysis

 - **Unsupervised dimensionality reduction**: The new features are created without the help of
    labels. The goal is to create new features that are useful for the clustering
    task.
        - Case: PCA, MDS/PCoA, Isomap, LLE, Laplacian Eigenmaps

## Spectral methods

**Spectral methods** are based on the eigenvectors of specially constructure matrices.
The top to bottom eigenvectors are used to defined new features. 

  - **Classical** (i.e., linear) methods provide a faithfull representation of the
    covariance structure.
        Case: PCA, MDS/PCoA

  - **Graph-based methods** provide a representation that is faithful to the
    connectivity structure of the data. They allows the analysis of 
    highly non-linear data sets.
        Case: Isomap, Local linear embeddings, Laplacian Eigenmaps

  - **Kernel methods**: They are a generalization of the graph-based methods. They
    allow the analysis of non-vectorial data, meaning they are not represented
    as a matrix. Many linear methods can be generalized to non linear-kernel methods.

        Case: Kernel PCA, Kernel MDS/PCoA, Kernel Isomap, Kernel LLE, Kernel Laplacian Eigenmaps

They can also be distinguished based on the eigendecomposition of a **full
matrix** or a **sparse matrix**. See van der Maaten and al., (2009) for a
comparison of full and sparse spectral methods.

##

## References
Saul, L. K., Weinberger, K. Q., Sha, F., Ham, J., & Lee, D. D. (2006). Spectral methods for dimensionality reduction.

