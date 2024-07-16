# Unsupervised Machine Learning (module_19 challenge)

## Crypto Clustering 

### Data Loading
1. Load `crypto_market_data.csv` into a DataFrame.

### Data Preparation
1. Normalize the data using `StandardScaler()` from scikit-learn.
2. Create a DataFrame with the scaled data, using "coin_id" from the original DataFrame as the index and display the first five rows of the scaled DataFrame. 

### Determine Optimal k Value with Original Data
1. Apply the elbow method to find the best k value:
   - Generate a list of k values from 1 to 11.
   - Compute inertia for each k value and store the results.
   - Plot the inertia values to identify the optimal k visually and record it. 

### Cluster Cryptocurrencies with Original Data
1. Initialize and fit a K-means model with the identified k value.
2. Predict clusters using the original scaled DataFrame.
3. Add the predicted clusters to a copy of the original DataFrame.
4. Create a scatter plot with hvPlot:
   - X-axis: `price_change_percentage_24h`
   - Y-axis: `price_change_percentage_7d`
   - Color by K-means labels
   - Hover info: `coin_id`

### Optimize Clusters with PCA
1. Perform PCA on the original scaled DataFrame, reducing to three principal components.
2. Calculate the total explained variance of these components.
3. Create a DataFrame with PCA data, setting "coin_id" as the index.
4. Verify the first five rows of the PCA DataFrame.

### Determine Optimal k Value with PCA Data
1. Use the elbow method to find the best k value for PCA data:
   - Generate a list of k values from 1 to 11.
   - Compute inertia for each k value and store the results.
   - Plot the inertia values to identify the optimal k visually.
2. Record the best k value and compare it to the original data’s k value.

### Cluster Cryptocurrencies with PCA Data
1. Initialize and fit a K-means model with the identified k value using PCA data.
2. Predict clusters using the PCA DataFrame.
3. Add the predicted clusters to a copy of the PCA DataFrame.
4. Create a scatter plot with hvPlot:
   - X-axis: `PC1`
   - Y-axis: `PC2`
   - Color by K-means labels
   - Hover info: `coin_id`

### Visualize and Compare the Results 
1. Create a composite plot by using hvPlot and the plus sign (+) operator to compare the elbow curve that you created from the original data with the one that you created from the PCA data.
2. Create a composite plot by using hvPlot and the plus (+) operator to compare the cryptocurrency clusters that resulted from using the original data with those that resulted from the PCA data.
