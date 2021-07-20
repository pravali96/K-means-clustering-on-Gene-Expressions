# Using Kmeans clustering to identify 5 cancer types
Performed K-Means clustering on a real world Genome Atlas. This dataset is available from the UC Irvine Machine Learning Repository. Data contains gene expressions from 5 distinct cancer subtypes. There are 881 samples (rows) and 20,531 gene expressions (columns).

#### Preprocessing
The labels for cancer types are in string format. Hence, I used label encoder to transform them to a numerical format. Since the data has large number of dimensions, I reduced 20,531 columns to 2 columns using PCA. For this, I built pipelines for feauture scaling and performing Principal Component analysis. I have use MinMax scaler so that the data doesnt have to follow a normal distribution.

#### Modeling using K_means clustering
Next, I built another pipeline for performing Kmeans clustering. Since there are 5 cancer types, I initialized k to be 5 and fit the tranformed data from PCA.

#### Model Evaluation
In order to evaluate the model, I used Silhouette coefficient and attained a score of 0.51. As ground truth labels are provided in the dataset,  I performed ARI to calculate adjusted Rand Score to compare ground truth labels with predicted labels and rand score came to be 0.72.

#### Visualization
Visualized the clusters in 2D space by using principal components. The model performed good but there was a slight overlap cuased from squishing 20,531 dimensions to 2 dimensions. 

#### Tuning the model
In order to improve the model, I calculated silhouette coefficient and Rand scores for all the principal components ranging from 2 to 11 and plotted the scores using a line chart. Rand score improved to 0.95 when number of principal components is equal to 7.
