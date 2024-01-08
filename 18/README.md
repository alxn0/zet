# Graph theory glossary

## Structure

| Concept                   | Definition                                                                                      | Symbol |
|---------------------------|-------------------------------------------------------------------------------------------------| ------ |
| Vertex                    | Elements                                                                                        | $V$    |
| Edges                     | Connections or relations                                                                        | $E$    |
| Undirected/ directed edge | Edge without/with orientation                                                                   |        |
| Connected graph           | Graph were every pairs of vertices are connected                                                |        |
| Connected component       | Connected subgraph of an undirected graph                                                       |        |
| Tree                      | Undirected connected graph in which all pairs of vertices are connected by one path             |        |
| Forest                    | Graph were all connected components are tree                                                    |        |
| Dendrogram                | Visual representation of a tree were the *root* is one one side and the leafs on the other side |        |


## Global Metric

| Metric  | Definition                                                              | Calculation |
|---------|-------------------------------------------------------------------------|-------------|
| Size    | Number of nodes                                                         | $\|V\|$       | 
| Density | Ratio of the number of edges with respect to the maximum possible edges | $D = \frac{2\|E\|}{\|V\|(\|V\| - 1)}$[^note1]  | 

[^note1]: Calculation for an undirected simple graph
