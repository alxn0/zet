# Feature selection and extraction (Jia and al., 2022)

 - **Feature selection**: Also called variable selection of feature subset selection, the goal
    is to find the most important features to simplify the models. The
    assumption is that there are redundant variables that can be removed
    without losing too much information.

 - **Feature extraction**: Create new features which are mapping of the original features. The
    new features are linear or non-linear combinations of the original
    features, which compress the information in the original
    features. Yet, the new features may have a different meaning, and
    be hard to interpret. Most of what we is discussed about
    dimensionality reduction are in fact feature extraction methods.

## Linear and non linear methods

 - **Linear methods**: The new features are linear combinations of the original features. 

 - **Non-linear methods**: The new features are non-linear combinations of the original features.

## Supervised and unsupervised dimensionality reduction

 - **Supervised dimensionality reduction**: The new features are created with the 
    help of labels (i.e., prior information on the objects). The
    goal is to create new features that are useful for the prediction
    task. 

 - **Unsupervised dimensionality reduction**: The new features are created without the help of
    labels. The goal is to create new features that are useful for the clustering
    task. 

## Spectral methods

Spectral methods are based on the eigenvectors of the data matrix which
are used to create new features



## References


Jia, W., Sun, M., Lian, J., & Hou, S. (2022). Feature dimensionality reduction: A review. 
Complex & Intelligent Systems, 8(3), 2663–2693. https://doi.org/10.1007/s40747-021-00637-x

