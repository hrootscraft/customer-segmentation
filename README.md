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

### Brief insights
1. KMeans

<div style="display:flex; justify-content:space-between;">
  <img src="https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/PCA1.png" width="45%" alt="PCA1">
  <img src="https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/TSNE1.png" width="45%" alt="TSNE1">
</div>

![img](https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/SHAP1.png)

2. KPrototype

<div style="display:flex; justify-content:space-between;">
  <img src="https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/PCA2.png" width="45%" alt="PCA2">
  <img src="https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/MCA2.png" width="45%" alt="MCA2">
</div>

![img](https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/SHAP2.png)

3. KMeans with Sentence Embeddings

<div style="display:flex; justify-content:space-between;">
  <img src="https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/PCA3.png" width="45%" alt="PCA3">
  <img src="https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/TSNE3.png" width="45%" alt="TSNE3">
</div>

![img](https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/SHAP3.png)

