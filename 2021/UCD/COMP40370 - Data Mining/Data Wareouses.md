# COMP40370 Data Mining, Data Warehouses 

## From tables and spreadsheets to data cubes

- Multidimensional data model
    - Views data in the form of a data cube
    - The lattice of cuboids forms a data cube
- Data cube
    - Allows data to be modelled and viewined in multiple dimensions
- Dimension tables represent dimensions
- Fact tables 
    - Contain keys to each of the related dimension tables and measures
    - Fact table -> Dimensions + Measures

## Cube: A lattice of Cuboids
- N-Dimentional base cube is called a cuboid
- The top most 0-D cuboid, which holds the highest-level of summarisation, is called the apex cuboid

## Data warehouse models

- **Star Schema**, a fact table in the middle connected to a set of dimensions
- **Snowflake Schema**, a refinement of the start schema where some dimensional hierarchy is normalised into a set of smaller dimensional table,s forming a shape similar to a snowflake
- **Fact Constellation**, Multiple fact tables share dimensional tables, viewed as a collection of stars, therefore called galaxy schema or fact constellation

