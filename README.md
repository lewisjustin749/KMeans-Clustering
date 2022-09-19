# KMeans-Clustering
Clustering tasks on the HR dataset. Objective is to categorize the candidates into two categories with the hope that it may be able to categorize the two types of candidates and put them into the different clusters.

**Dataset**

hrdata3.csv 

The dataset is a modified version of the hrdata set that you have used for A1 and A3. This version has very few columns and all of which are numerical columns and ready to apply kmeans. 

**Introduction**

In this assignment, you have to perform clustering tasks on the given dataset. Our objective is to categorize the candidates into two categories with the hope that it may be able to categorize the two types of candidates and put them into the different clusters. As we have the ground truth of the data, we can also try evaluate whether it was able to categorize them or not. However, note that in general, you may not have the ground truth to evaluate a cluster like this. 

For each section, you must have to put the question (with question number) and an appropriate header text as a text cell. And after the header, you can use multiple cells for coding and explaining, and plotting.

**Tasks:**

**1.Load Data and perform basic EDA**

   * import libraries necessary libraries 
   * import the data to a dataframe and show the count of rows and columns (1 pt)
   * Show the top 5 and last 5 rows (1 pt)
   * Is there any null values on any column?
   * Are all the columns numeric such as float or int? If not, please convert them to numeric (int/float) before going to the next step.
   * plot the heatmap with correlations to get some more idea about the data.
 
**2.Feature Selection and Pre-processing**
  * Put all the data from the dataframe into X, except the enrolle_id and the target columns
  * Perform feature scaling on the data of X with StandardScaler and show some sample data from X after scaling (Use the technique shown in the second answer from this post: https://stackoverflow.com/questions/44552031/sklearnstandardscaler-can-i-inverse-the-standardscaler-for-the-model-output (Links to an external site.) )

**3.KMeans Clustering**
  * Import related library for Kmeans and perform Kmeans on X (note that it was scaled already). Make sure to put random_state = 47 (it can be any number, but use 47 so that you will produce almost the same result as us). Use k-means++ for the initial centroids. You should know from the problem description how many clusters we are interested in.
  * Show the cluster centers as it is and then inverse the scale and show the centers. Please explain in words about the centers relating them to the columns of the data set
  * Show the distance matrix
  * Show the labels
  * Add a new column to your data frame called cluster_label and assign the cluster label for the instances based on the K-means cluster label
  * The target column of our data frame is floating-point numbers. So, this number is not comparable with the cluster label. Add a column target_int and write a function or use a strategy to store the int version of the target column into the target_int column (For example, 1.0 in the target will be 1 in the target_int, 0.0 will be 0)
  * Show the top 5 rows of the dataframe now that shows you have added those two columns and they have the correct values
  * Now, we would like to compare the cluster label with the ground truth. Print confusion matrix that compares the target_int and the cluster_label, show the classification_report, and then show the total number of misclassification.
  * Discuss the numbers from 3 Viii and any thoughts on it.
  * Show the inertia of the cluster
  * What is the elbow method and what is its purpose of it in the case of KMeans clustering?
  * Although we just wanted 2 clusters, we still would like to see what will happen if you increase the number of clusters. Plot the inertia for the different numbers of clusters from 2 to 20. 
  * Show a scatter plot with training hours against experience where the points should be colored based on the two cluster labels. Write any thoughts on this plot.
  * Show a scatter plot with any other two attributes you are interested in like 3 Xiii and add your thoughts on your plot as well

**4.AgglomerativeClustering (Helping recourse for the relevant codes:  https://www.analyticsvidhya.com/blog/2019/05/beginners-guide-hierarchical-clustering/ (Links to an external site.) )**
  * Plot a dendrogram (make the figure size relatively big, but still you will not be able to see it completely. However, it least this will give you an idea on how many cluster would you like to generate)
  * Perform AgglomerativeClustering with 2 clusters first, and use euclidean distance for affinity and linkage = 'ward' 
  * After creating the clusters, plot training hours against experience like 3.Xiii and discuss if anything interesting
  * Then, increase the number of clusters to 4 or 5 and build the clusters again and plot them again to see any difference.
