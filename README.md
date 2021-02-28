# Cryptocurrency_ML_Analysis
Unsupervised Machine Learning in Cryptocurrencies

## Background
Accountability Accounting, a prominent investment bank, asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment. The data retrieved from CryptoCompare is not ideal, so it will need to be processed to need to be processed to fit the machine learning models. We will use the clustering algorithm for the cryptocurrencies to share her flndings with the group.


## Objects
1. Preprocess cryptocurrency data for unsupervised learning.
2. Reducing Data Dimensions Using Principal Component Analysis (PCA) to limit features and speed up the model.
3. Cluster data using the K-means algorithm and determine the best amount of centroids for K-means using the elbow curve.
4. Visualizing Cryptocurrencies Results with scatter plots with Plotly Express and
hvplot.

## Software/Tools/Libraries
* Jupyter Notebook 6.1.4 with numpy, pandas, hvplot,  pathlib, plotly.express.   scikit-learn with StandardScaler, MinMaxScaler, decomposition with PCA, cluster with KMeans.

* Data Source: 
The crypto_data.csv was retrieved from CryptoCompare (https://minapi.
cryptocompare.com/data/all/coinlist).

## Results

### Task 1: Preprocessing the Data for PCA

* Using the knowledge of Pandas, import and preprocess the crypto_data.csv in order to perform the Principal Component Analysis (PCA)


* A clean DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame and standardized using the StandardScaler

![Scaled_df](image/Scaler.png)

### Task 2: Reducing Data Dimensions Using PCA

* Using the knowledge of the Principal Component Analysis (PCA) algorithm, reduce the dimensions of the X DataFrame to three principal components, and place these dimensions in a new DataFrame

* The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components, PC 1 , PC 2 , and PC 3, and has the index from the crypto_df
DataFrame.

![pca_df](image/three_pca.png)


### Task 3: Clustering Cryptocurrencies Using K-means

* Using the knowledge of the K-means algorithm, create an elbow curve using  hvPlot to find  the best value for K. Then, run the K-means algorithm to predict
the K clusters for the cryptocurrencies’ data.

* Elbow Curve to find the best value for K

![Elbow_curve](image/Elbow_curve.png)

* Prediction on the K clusters of the cryptocurrencies

![Prediction](image/Prediction.png)

* Create a new DataFrame including predicted clusters and cryptocurrencies features

![clustered_df](image/clustered_df.png)



I started by cleaning up the data to only have cryptocurrencies that are actively trading, have a defined algorithm, and have a complete set of data. This left me with 532 different cryptocurrrencies. From there I created a three dimisional graph to show how the different cryptocurrencies are grouped together. Each point includes its name as well as the algorithm used to create the currency.

![clustered_3d](https://github.com/Wall-E28/cryptocurrencies/blob/main/visualizations/clustered_3d.png)

After that, I created a two dimisional graph to show the relationship between total coin supply and total coins mined to show how each currency compares to the rest. Each point includes its currency name.

![coins_2d](https://github.com/Wall-E28/cryptocurrencies/blob/main/visualizations/coins_2d.png)

## Summary

From the three dimisional graph, You can see that there are four different groups. Two groups are clumped very closely together with most currencies falling into one of these two groups. One group has a few different currencies that are farther away from the others and then there is the last group that only have one currency. This shows that there are lot of currencies that perform similarly while there are a few that are outliers. These outliers could be over performers or under performers, but I would need to perform more analysis to figure that out. One thing that I can connect is by looking at the total coin supply vs total coins mined graph. The two main groups have most of there data points scattered between 0% and 40% of the largest currency based on volume. The group with a few currencies are are very close to 0% of the largest currency, while the group with just one currency is at 100% as it is the largest currency.

I would want to complete further analysis on these cryptocurrencies by looking at their historical pricing to understand the performance of each of these currencies. This would help investors now how stable or risky their investment would be based on the the different cryptocurrencies they invest in.