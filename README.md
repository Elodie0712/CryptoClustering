In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/6637d3d0-6400-4dc9-97a1-4b139a7995ee)

Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/1bee1a69-ecef-4a50-8ca7-c69fe6b6e4d1)

The first five rows of the scaled DataFrame should appear as follows:
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/462654d7-34fe-4185-8241-528bc45d7087)

Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best value for k using the following steps:

Create a list with the number of k values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.

![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/ee04f6a7-9c47-421c-ba13-7af6d74e140e)

Create a dictionary with the data to plot the elbow curve.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/26f44ea8-014b-4b48-bc3e-21e1ac58c40c)

Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/ae02d302-5df7-4f87-b5dd-0ef4d0f21caa)

Answer the following question in your notebook: What is the best value for k? 

Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

Initialize the K-means model with the best value for k.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/09ed2820-0f2a-41b5-8239-b9f396985e76)

Fit the K-means model using the original scaled DataFrame.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/ef51c977-06fe-441e-a2f5-d47fac4a9315)

Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/992a03a2-bce3-42e1-a302-124b1a4fd5cf)

Create a copy of the original data and add a new column with the predicted clusters.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/c47570f5-f530-48e0-937f-63d797846b10)
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/0090ed18-7b99-4c51-a4d6-2bb3bd3334b3)

Create a scatter plot using hvPlot as follows:
Set the x-axis as "PC1" and the y-axis as "PC2".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/6cddf399-ac99-49a1-b9f1-17994c04287a)
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/1d593ded-080b-464e-af18-0f2281998325

Optimize Clusters with Principal Component Analysis
Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/322979bb-e275-4c4b-9d3e-dca66daa949b)

Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/f3bbc7e8-64f7-4b9f-9c6d-c27bbeb3990a)

What is the total explained variance of the three principal components?
Total explained variance ≈ 0.37805 + 0.28257231 + 0.23321016
≈ 0.89383247 *100 ≈ 89.38%
Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/d4d764a3-1967-4072-9812-2a73894c4ec7)

Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:

Create a list with the number of k-values from 1 to 11.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/b469e7d6-f75d-42d3-83c0-bceff074d5d8)

Create an empty list to store the inertia values.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/bde6bb35-fdbd-42de-870b-668448964dbb)

Create a for loop to compute the inertia with each possible value of k.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/9933f104-275f-4609-91eb-06f5e5fe38ff)

Create a dictionary with the data to plot the Elbow curve.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/cbf3298c-c391-4a83-ba50-9337794bbbb0)

Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/59100cae-71fd-4321-bd15-1f22dd1fc289)

 **Question:** What is the best value for `k` when using the PCA data?

  * **Answer: 4

* **Question:** Does it differ from the best k value found using the original data?

  * **Answer:No, it does not differ from the besk k value using the original data
 
Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialize the K-means model with the best value for k.

Fit the K-means model using the PCA data.

![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/a87b6586-5d81-4747-9e45-5ec8186bf1e2)

Predict the clusters to group the cryptocurrencies using the PCA data.

![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/a8d461dd-d89d-4964-bcc5-a0b3d4fdd76a)

Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.

![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/a5a7c10a-d700-4299-9931-a6d34e9fb7a9)

Create a scatter plot using hvPlot as follows:
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/31197620-5848-4fe4-90d9-0e240ada184e)

![image](https://github.com/Elodie0712/CryptoClustering/assets/148305373/e1490171-7620-4d93-901f-056ab31363b7)

Answer the following question:
What is the impact of using fewer features to cluster the data using K-Means?Although the Elbow Curves generated from both K-means and PCA methods exhibit similarities, employing the PCA technique with a reduced set of features for clustering purposes led to the emergence of more distinct and easily recognizable clusters compared to those identified using the K-means approach.

