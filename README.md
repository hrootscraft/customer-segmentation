# Customer Segmentation using Advanced Techniques
<sup>Unsupervised Machine Learning Project</sup>

The project aims to analyze and cluster customers based on various features, including numerical and categorical variables. 
Three different methods are explored: K-Means, K-Prototype, and a combination of Sentence Embeddings with K-Means.

### Concepts applied: 
- Univariate and Bivariate Analysis,
- Handling outliers using ECOD (Empirical Cumulative Distribution Functions) class of [PyOD (Python Outlier Detection)](https://github.com/yzhao062/pyod) library
- PCA, MCA, t-SNE for visual evaluation of models,
- Silhouette Plots and Elbow Curve to get 'K',
- LightGBM to see how well the clusters are distinguished (scoring done on F1 score),
- SHAP values to gain an insight into which features are contributing more to the model.
