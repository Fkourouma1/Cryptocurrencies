# Cryptocurrencies
# Overview
This project is about an investment bank which is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, we will create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment. Because the company has no output for what it is looking for, we will machine unsupervised learning to process, fit, transform and visualize our findings.

We will processed using four deliverables:
## Deliverable 1 
From the data that we have, we want to make sure:
- All cryptocurrencies that are not being traded are removed
- The IsTrading column is dropped
- All the rows that have at least one null value are removed

![drop_all-na](https://user-images.githubusercontent.com/103543959/194738917-914045f7-6e18-493d-ada5-903f7125a035.png)

- All the rows that do not have coins being mined are removed
- The CoinName column is dropped

![crypto_df](https://user-images.githubusercontent.com/103543959/194739014-e8487329-c635-4f91-966b-f16b20fd1366.png)

- A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame

The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X 
- The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function


## Deliverable 2 Requirements

- The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components
- The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame 

![Screen Shot 2022-10-09 at 12 14 17 AM](https://user-images.githubusercontent.com/103543959/194739288-16d95330-19f5-4332-8294-5dd6e38fa286.png)


## Deliverable 3 Requirements
- An elbow curve is created using hvPlot to find the best value for K

![Elbow_curve](https://user-images.githubusercontent.com/103543959/194739409-b95150a7-22a7-4ee5-aed6-9434c260cf56.png)


- Predictions are made on the K clusters of the cryptocurrencies’ data 
- A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class

![clustered_df](https://user-images.githubusercontent.com/103543959/194739427-818e64c0-ce19-4ae4-bb00-be09672bcd25.png)


## Deliverable 4 Requirements
- The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover 

![Screen Shot 2022-10-09 at 12 20 35 AM](https://user-images.githubusercontent.com/103543959/194739469-ab160bb8-8197-44d8-bedd-f95a5302c770.png)


- A table with tradable cryptocurrencies is created using the hvplot.table() function

![Screen Shot 2022-10-09 at 12 23 37 AM](https://user-images.githubusercontent.com/103543959/194739546-67b85592-ba68-4867-ae50-663b2accbc2d.png)

- The total number of tradable cryptocurrencies is printed
- A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns

![Screen Shot 2022-10-09 at 12 25 00 AM](https://user-images.githubusercontent.com/103543959/194739749-86a03d51-d668-4602-a010-d74599ecf12d.png)


- A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point

![Screen Shot 2022-10-09 at 12 28 05 AM](https://user-images.githubusercontent.com/103543959/194739742-3fc20aa7-5afa-4ce1-9d53-ec0ff697cdda.png)

