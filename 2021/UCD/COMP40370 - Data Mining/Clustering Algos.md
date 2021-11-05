###### tags: `COMP40370 - Data Mining`

# Clustering Algos

## CURE (Clustering Using Representatives)
- The main idea of CURE:
    - Stops te creation of a cluster hierarchy if a level consists of k clusters
    - Uses multiple representative points to evaluate the distance between clusters, adjusts will to arbitry shapred clusters and avoids single-link effect

### Drawbacks of Distance-Based Method
- Drawbacks of square-error based clustering method
    - Consider only one point as represntatitve of a cluster
    - Good only for convex shaped, similar size and density, and if k ca be reasonably estimated

## Clustering Categorical Data: ROCK
- ROCK: Robust Clustering using linKs
    - Use links to measure similarity/proximity
    - Not distance based
    - Computational complexity
- Basic ideas
    - Similarity function and neighbours
- Links: the number of common neighbours for the two points
- Algorithm: Draw random sample (get a random sample of the data)
- Cluster the data using the link agglomerative approach
- Label data in disk

## Density-Based Clustering: Background
- Two parameters:
    - Eps: Maxiumum radius of the neighbourhood
    - MinPts: Minimum number of points in an Eps-neighbourhood of that point
- Directly Density-reachable: a point p is directly density reachable from a point q with regards to Eps, MinPts if:
    - p belongs to Neps(q)
    - Core point condition:
        - |Nepis(q)|
- Density-reachable:
    - A point p is density-reachable from a point q with regard to Eps, MinPts if there is a chain of points p1, ... pn, = q, pn=p such that p_i+1 is directly density-eachable from p_i
- Density-connected
    - A point p is density-conneced to a point q with reard to Eps, MinPts if there is a point o such that both, p and q are density-reachable from ow ith regard to Eps and MinPts

## DBSCAN
- DBSCN: Density Based Spatial Clustering of Applications with Noise
- Relies on a density-based notion of cluster; A cluster is defined as a maimal set of denisty-connected points
- Discovered clusters of arbitrary shape in spatial databases with noise
- Algo:
    - Arbitrary select a point..
    - Retrieve al points density-reachable from p with regard to Eps and MinPts
    - if p is a core point, a cluster is formed
    - if p is a border point, no points are density-reachable from p and DBSCAN visists the next point of the database
    - Continue the process until all of the points have been processed
