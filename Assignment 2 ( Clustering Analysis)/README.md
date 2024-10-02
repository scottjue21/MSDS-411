## Assignment 2: Identifying Housing Submarkets using Clustering Analysis

This project demonstrates the use of unsupervised learning methods, specifically clustering analysis, to identify distinct housing submarkets within a dataset from Melbourne's real estate market. The dataset, consisting of 21 columns and 34,857 rows of data, includes various property attributes such as location, type, price, and size. The aim of this project is to gain valuable insights that can support real estate firms in their decision-making processes related to marketing, property valuation, and outlier detection.

### Methodology

The analysis begins with data preprocessing, including an outlier search and scaling of the dataset to ensure all variables contribute equally to the clustering process. Two clustering techniques, hierarchical clustering and k-means clustering, were employed and compared to determine the optimal number of clusters. Hierarchical clustering was performed using three linkage methods (complete, average, single), and dendrograms were evaluated for practicality and interpretability. K-means clustering was then applied, with the optimal number of clusters identified using both the within-cluster sum of squares method (elbow-point) and gap statistic.

Based on the results, k-means clustering was selected as the final method, with 4 clusters providing the best fit. Summary statistics were calculated for each cluster, and cluster plots were created to visualize the segmentation of the dataset.

### Results

The k-means clustering model identified four meaningful subgroups within the Melbourne housing dataset:

- **Cluster 1**: Smaller, less expensive properties located further from the city center. These properties tend to be newer with fewer rooms and a smaller land size.
- **Cluster 2**: Larger, more expensive properties situated closer to the city center. This cluster has the highest mean price and larger building areas.
- **Cluster 3**: Moderately sized and priced properties located further from the city center, with a higher proportion of house/cottage-type dwellings.
- **Cluster 4**: Larger, more expensive properties located at a moderate distance from the city center, with the oldest average year built and a larger land size.

These clusters provide real estate firms with actionable insights into housing submarkets, helping them identify key segments based on property type, size, price range, and location. 

### Conclusion

This project demonstrates how k-means clustering can be effectively utilized to segment a large real estate dataset into meaningful submarkets. By leveraging this technique, real estate firms can develop targeted marketing strategies, improve property valuation precision, and enhance decision-making across various aspects of real estate transactions. Ultimately, clustering analysis provides a valuable tool for gaining a competitive edge in the real estate market.

### Contributors

This project was a collaborative effort by the following team members:

- David Caban
- Bronsin Jabraeili
- Scott Jue
