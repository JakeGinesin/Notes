 ###### tags: `COMP40370 - Data Mining`
 
 # Clustering
 
 > Objectives:
 > Understanding clustering analysis
 > Types of data in clustering analysis
 > major clustering methods
 > partitioning methods
 > hierachal methods

## Cluster Analysis
- Cluster
    - Collection of data objects similar to one another within the same cluster
    - dissimilar to the objects in other clusters
- Clustering
    - Grouping is a set of data bjects into clusters
    - is an *unsupervised classification*
    - **no** predefined classes
- Typical applications
    - *Stand-alone tool* to get insight into data distribution
    - *Pre-processing step* for other algorithms

## Clustering Applications
- Pattern recognition
- Image processing
- Economic Science (market research especially)
- Special Data analysis
    - Create thematic maps in GIS by clustering feature spaces
    - detect spatial clusters and explain them in spatial data mining
- Marketing
    - Helps marketers discover distrinct groups in their customer bases, and then use this knowledge to develop targeted marketing programs
- Insurance
    - Identifying groups of motor insurance policy holders with a high average claim cost
- City Planning
    - Identifying groups of houses accordin to their house type, value, and geographical location
- Earthquake studies
    - Observed earth quake epicentres should be clustered along continent faults

## Good Clustering
> Good clustering vs bad clustering...

- A *good clustering* method will produce high quality clusters with
    - high intra-cluster similarity
    - low inter-cluster similarity
>
- Clustering quality
- Depends on both the similar measured use by the method and its implementation
- is also measured by its ability to discover all or some of the hidden patterns

## Clustering Requirements
- Scalabiliy
- Ability to deal with:
    - different types of attributes
    - noise and outliers
- Discovery of clusters with arbitrary shape
- Minimal requirements for domain knowledge to determine input parameters
- insensitive to order of input records
- incorperation of user-specified constraints
- interpretability and usability

## Measure the Qualiy of Clustering
- Dissimilarity/Similarity metric
    - Similiarity is expressed in terms of a distance function, which is typically metric: d(i,j)
- The definitions of distance functions are usually very different for interval-scaled, boolean, categorical, ordinal, and radio variables
- Weights should be associated with different variabled based on applicatios and data semantics
- it is hard to define "similar enough" or "good enough"
    - the answer is typically highly subjective



