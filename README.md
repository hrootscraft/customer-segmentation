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

![alt1](https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/SHAP1.png)
![alt2](https://github.com/hrootscraft/customer-segmentation/blob/aa1d7b8d75960073b6bc065bf58113d4654944a5/assets/CI1.png)

- Clusters with job=blue-collar do not have distinct differences between their characteristics, except the age feature. This is not desirable since it is difficult to differentiate the clients in each cluster.
- In the job=management case, we obtain better differentiation wrt education and balance.



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

![alt3](https://github.com/hrootscraft/customer-segmentation/blob/e276a99b300f004f9acc7a1e809eda795397f5f1/assets/SHAP3.png)
![alt4](https://github.com/hrootscraft/customer-segmentation/blob/aa1d7b8d75960073b6bc065bf58113d4654944a5/assets/CI3.png)

- In management, we see that the single managers are younger than the older married ones. And they have comparitively lesser bank balance than the married ones. This might be due to experience but we don't have that data.
- Overall,  Kmeans + Sentence Embedding model is optimal since it needs fewer variables to be able to give good predictions.

### Further Line of Thought:
- The model we employed is not well-suited for comparing numerical values in fields. For instance, the sentence "Salary = 10000" yields embeddings that are more similar to those of the sentence "Salary = 100000" than to the embeddings of "Salary = 11000." This limitation arises because the model excels at comparing text but treats numbers as characters rather than quantities. Consequently, only sentences related to job and marital status proved to be significant, as the model's strength lies in comparing textual information rather than numerical data.
- If you want to enhance the clustering performance on numerical data, you can consider the following modifications to the above method:

  **Hybrid Embedding:**
  Use a combination of sentence embedding for text features and a different embedding method for numerical features.
  For numerical features, consider using methods like PCA (Principal Component Analysis) or t-SNE (t-Distributed Stochastic Neighbor Embedding) to create embeddings.

  **Feature Engineering for Numerical Data:**
  Create additional text-based features from numerical fields. For example, instead of just "Salary = 10000," you could have "Salary is High," "Salary is Medium," "Salary is Low," etc. This way, numerical information is translated into text, making it compatible with the sentence embedding model.
