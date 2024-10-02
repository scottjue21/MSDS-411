# Assignment 1: Political Campaign Strategy Consulting Using Dimensionality Reduction Techniques

## Project Overview

This project applies unsupervised learning techniques—Principal Component Analysis (PCA) and Exploratory Factor Analysis (EFA)—to analyze the Pew Research Center’s political public opinion survey data. The objective was to uncover latent variables and trends that could inform political campaign strategies by reducing the complexity of the dataset while retaining key insights. R was used throughout the analysis, leveraging its powerful data wrangling and visualization libraries.

Survey data is often large and complex, posing challenges for interpretation and insight generation. By applying PCA and EFA, this project successfully reduced the dimensionality of the dataset, providing a clearer view of public sentiment on a variety of political and social issues. EFA was found to be the most effective method for this analysis, isolating seven key factors from the dataset’s 129 variables and 1,503 observations.

### Methodology

The analysis began with extensive data preparation, including cleaning the dataset, handling missing values by selecting complete cases, and converting the data into a matrix of binary indicators. Both PCA and EFA were applied to the refined data to compare their effectiveness in dimensionality reduction.

- **Principal Component Analysis (PCA)**: PCA reduced the dataset to 40 components, which captured the variability across the original variables. However, the high number of components made interpretation challenging.
- **Exploratory Factor Analysis (EFA)**: EFA was more efficient, reducing the dataset to 7 interpretable factors. Varimax rotation and principal axis factoring were used to optimize the results, providing a better fit for the data without requiring distributional assumptions.

Key steps involved computing the correlation matrix, visualizing eigenvalues through scree plots, and testing different rotation methods. The model fit was assessed through various statistical measures, such as the RMSEA index, which indicated a good fit to the data.

### Results

The EFA model revealed seven factors, each representing key dimensions of political sentiment, such as:

- Public perceptions of discrimination
- Attitudes toward the political environment
- Trust in the Federal Government
- Opinions on tax fairness
- Attitudes toward religion

These seven factors explained 45% of the variance in the data, with the remaining variance distributed across smaller factors. The EFA method also isolated 15 questions that could be used to create a regression tree, potentially allowing political analysts to predict a respondent’s political ideology with just a handful of questions. This increases the utility of the model for practical applications in political campaign strategy.

### Conclusion

The comparison of PCA and EFA showed that EFA is the more suitable method for analyzing political survey data. EFA not only simplifies complex data but also reveals underlying trends and latent variables that are essential for developing targeted political campaign strategies. By identifying key factors related to political ideology, discrimination, trust in government, and other issues, this analysis helps consulting teams gain actionable insights from large, complex survey datasets. Future applications could extend this work by developing new, more efficient questionnaires or predictive models for political leanings.

### Contributors

This project was a collaborative effort by the following team members:

- David Caban
- Bronsin Jabraeili
- Scott Jue
