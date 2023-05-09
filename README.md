# Cryptocurrencies Clustering

## Background

The Cryptocurrencies Clustering project predicts if cryptocurrencies are affected by 24-hour or 7-day price changes using unsupervised learning techniques like K-means clustering.

Also, the project explores the impact of reduction of number of features using Principal Component Analysis (PCA) on clustering.

## Steps

* Load the data.
* Use StandardScaler() module from scikit-learn to normalize the data.
* Find the best value of k using the original scaled data by applying elbow method.
* Cluster cryptocurrencies with K-means using the original scaled data.
* Optimize Clusters with PCA.
* Find the best value for k using the PCA data.
* Cluster cryptocurrencies with K-means using the PCA data.
* Visualize and compare the results using hvPlot.


### Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

* Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
* Find the Best Value for k Using the Original Scaled DataFrame
* Use the elbow method to find the best value for k using the following steps:
* Create a list with the number of k values from 1 to 11.
* Create an empty list to store the inertia values.
* Create a for loop to compute the inertia with each possible value of k.
* Create a dictionary with the data to plot the elbow curve.
* Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

### Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

* Initialize the K-means model with the best value for k.
* Fit the K-means model using the original scaled DataFrame.
* Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
* Create a copy of the original data and add a new column with the predicted clusters.
* Create a scatter plot using hvPlot as follows:
    * Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
    * Color the graph points with the labels found using K-means.
    * Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### Optimize Clusters with Principal Component Analysis
Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

Retrieve the explained variance to determine how much information can be attributed to each principal component 

Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

### Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:

* Create a list with the number of k-values from 1 to 11.
* Create an empty list to store the inertia values.
* Create a for loop to compute the inertia with each possible value of k.
* Create a dictionary with the data to plot the Elbow curve.
* Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

### Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

* Initialize the K-means model with the best value for k.
* Fit the K-means model using the PCA data.
* Predict the clusters to group the cryptocurrencies using the PCA data.
* Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
* Create a scatter plot using hvPlot as follows:
* Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
* Color the graph points with the labels found using K-means.
* Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.


## Results

The project includes the following visualizations:

Elbow curve for the original data.
![elbow](https://github.com/patelavani332/CryptoClustering/assets/120197958/a8136b42-f1dd-45ad-a9dd-07c536076423)

Elbow curve for the PCA data.
![pca_elbow](https://github.com/patelavani332/CryptoClustering/assets/120197958/7c336e88-d255-4607-9a8d-357571f8fb52)

Scatter plot of cryptocurrency clusters based on the original data.
![crypto](https://github.com/patelavani332/CryptoClustering/assets/120197958/0cea5699-6ad0-41e8-8d16-527cffa9207c)

Scatter plot of cryptocurrency clusters based on the PCA data.
![pca_cluster](https://github.com/patelavani332/CryptoClustering/assets/120197958/20a24b42-f1e3-4956-949e-41c28aaf6d54)


## Dependencies

This is a Python project ran using a Jupyter notebook in a conda Dev environment.

The following dependencies are used:

Jupyter Notebook - Running code

Pandas - Data analysis

hvPlot - Interactive Pandas plots

scikit-learn - KMeans clustering, data normalization, and PCA

     import pandas as pd
     import hvplot.pandas
     from sklearn.cluster import KMeans
     from sklearn.decomposition import PCA
     from sklearn.preprocessing import StandardScaler
    
### Installations required

In anaconda prompt terminal for windows 

    pip install sklearn    
    pip install -U scikit-learn    
    pip install hvplot    
    conda install -c pyviz hvplot
    
    
 
