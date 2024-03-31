# Traditional clustering algorithms

Here's a quick categorial overview of some of the mostly used *traditional* clustering
methods.

Most of this information is taken from Xu and Tian (2015) and
Ezugwu and al. (2022). See those paper for an extensive review of
methods.

<table>
 <tr>
   <th>Category </th>
   <th>Exemple</th>
   <th>Logic</th>
   <th>Advantages</th>
   <th>Limitations</th>
 </tr>
 <tr>
   <td>Hierarchical-based</td>
   <td>Single-linkage</td>
   <td>Clusters are merged or split based on minimal/maximal
 distances between objects, or between cluster centroids. </td>
   <td>
       <ul>
           <li>Easy to implement and to interpret</li>
           <li>Allows to explore hierarchical clustering structure</li>
           <li>Can be used with arbitrary distances</li>
       </ul>
   </td>
   <td>
       <ul>
           <li>High computational cost in general (limited with big data)</li>
           <li>wrong <i>connection</i> can't be undone, need a cutpoint for k cluster.</li>
       </ul>
   </td>
 </tr>
</table>


> All the following methods are partitionnal-based methods, meaning that they
produce a single partition of the data, in contrast with previous
hierarchical-based methods

<table>
 <tr>
   <th>Category </th>
   <th>Exemple</th>
   <th>Logic</th>
   <th>Advantages</th>
   <th>Limitations</th>
 </tr>
 <tr>
   <td>centroid-based</td>
   <td>k-mean</td>
   <td>Represent each cluster according to a central vector
  (centroid). Centroid are move iteratively, and optimization is done
  on the square error distance to these centroids. Works well when
  cluster are compact and spherical. </td>
   <td>
       <ul>
           <li>Works well when cluster are compact and spherical</li>
           <li>Low computation cost and easy to implement</li>
           <li>Can be used with arbitrary distances with k-medoid</li>
       </ul>
   </td>
   <td>
       <ul>
           <li>Need to specify a priori number of cluster</li>
           <li>Biases towards spherical clusters</li>
           <li>Sensible to noise [^note1] </li>
           <li>sensitive to number of clusters</li>
           <li>Easily drawn to local optimal[^note2]</li>
       </ul>
   </td>
 </tr>
 <tr>
   <td>density-based</td>
   <td>DBSCAN</td>
   <td>Based on the objects space, conncect areas of high density
  into clusters. Allows for more arbitrary-shaped such as elongated dense
  or doghnut-like areas.</td>
   <td>
       <ul>
           <li>Non-biased toward specific shape.</li>
           <li>Robust to outliers</li>
       </ul>
   </td>
   <td>
       <ul>
           <li>Need to select appropirate parameters. 
           <li>Difficulties with varying density and high-dimensionnal data</li>
       </ul>
   </td>
 </tr>
</table>


> Distribution- and model-based methods involve a statistical framework with
> estimation and optimization of parameters.

<table>
 <tr>
   <th>Category </th>
   <th>Exemple</th>
   <th>Logic</th>
   <th>Advantages</th>
   <th>Limitations</th>
 </tr>
 <tr>
   <td>Distribution-based</td>
   <td>Gaussian mixture</td>
   <td>Assume the data is generated from
       a combination of probability distributions. The clustering process
       involves identifying these distributions (i.e., their parameters) and
       assiging objects to the most likely distribution. Distances from the
       distribution center define likelihood of belongings to a cluster.</td>
   <td>
       <ul>
           <li>More realistic to consider probability of belonging to a cluster</li>
           <li>Allows exploring overlapping clustering structure</li>
           <li>Hability to represent cluster of different sizes</li>
       </ul>
   </td>
   <td>
       <ul>
           <li>Initial paramaters strongly influence the clustering results</li>
           <li>Should not be used when having no clue on the data type of distribution</li>
       </ul>
   </td>
 </tr> 
 <tr>
   <td>Model-based</td>
   <td>COBWEB</td>
   <td>Takes a more general approach to the previous
  distribution-based methods by fitting the data to a model that is not
  defined strictly in terms of probability distribution, such as
  statistical learning and neural networks.
  </td>
   <td>
       <ul>
           <li>More complex models allows a greater flexibility than distribution-based models</li> 
           <li>Clusters can be described by the underlying model</li>
       </ul>
   </td>
   <td>
       <ul>
           <li>Relative high time complexity</li>
           <li>Can be difficult to select the right models</li>
           <li>Potential for overfitting</li>i
           <li>Clustering sensitive to parameters.</li>
       </ul>
   </td>
 </tr>
</table>

> The next approach is designed for non strict/overlapping clusters

<table>
 <tr>
   <th>Category </th>
   <th>Exemple</th>
   <th>Logic</th>
   <th>Advantages</th>
   <th>Limitations</th>
 </tr>
 <tr>
   <td>Fuzzy-based</td>
   <td>Fuzzy c-means</td>
   <td>Cluster are defined as fuzzy sets in which objects
       simultaneaously belongs to multiple clusters. The discrete belongin to
       cluster {0, 1} is changed to a continuous interval [0, 1]. Objects are assigned to
       clusters with various level of membership, implying overlapping
       clusters. 
   </td>
   <td>
       <ul>
           <li>More realistic to have different degree of belongin to cluster</li>
       </ul>
   </td>
   <td>
       <ul>
           <li>Local Optimum</li>
           <li>Sensitive to initial parameters</li>
           <li>Number of clusters need to be preset</li>
       </ul>
   </td>
 </tr> 
</table>

## References
Xu, D., & Tian, Y. (2015). A comprehensive survey of clustering algorithms. Annals of Data Science, 2, 165–193. <https://doi.org/10.1007/s40745-015-0040-1>

Ezugwu, A. E., Ikotun, A. M., Oyelade, O. O., Abualigah, L., Agushaka, J. O., Eke, C. I., & Akinyelu, A. A. (2022). A comprehensive survey of clustering algorithms: State-of-the-art machine learning applications, taxonomy, challenges, and future research prospects. Engineering Applications of Artificial Intelligence, 110, 104743. <https://doi.org/10.1016/j.engappai.2022.104743>

[^note1]: Although k-medoid is more robust than k-mean
[^note2]: A workaround is to compute multiple iterations with different
    starting point for centroids.
