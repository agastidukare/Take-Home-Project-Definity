# Take-Home-Project-Repo
This repo hosts 3 notebooks created as a part of Definity's Take-Home Project for Poland cars for sale dataset challenge.

You can find the dataset here:
https://www.kaggle.com/datasets/bartoszpieniak/poland-cars-for-sale-dataset

The Dataset hosts Ads posted on the car dealership website between March 2021 to May 2021. Most of the cars are from Poland but there are cars also
from other regions. The dataset is mostly clean with some of the columns having missing entries. 

I performed 3 tasks on the dataset: Vehicle Segmentation, Anomaly Detection & Time-Series Analysis. Each task has a separate notebook. 

Here are approaches & findings from each of them

**Vehicle Segmentation:**
The goal of this task is to segment or group vehicles having similar characteristics. For this task, after doing basic EDA, I found out 
that the data has some outliers & missing values. I needed to do imputation & scaling to make the data cleaner & have the same scale since the features
had varying scales. I experimented with KMeans & GMM. Utilizing KMeans helped me to group cars with similar prices, engine power & age to cluster
together while GMM highlighted cars with anomalous characteristics.

GMM was better at spotting anomalies since it's a probabilistic approach and doesn't assume spherical clusters. Thus it's good with clusters
with lots of overlaps.

**Anomaly Detection:**
The goal of this task was to spot anomalies in data. The challenge here was that 50% of columns indicating vehicle properties had a large chunk of data missing. To 
tackle this, I used group imputation. For modeling, I used isolation forest owing to the high dimensionality of our data & less computation cost. I tried DBSCAN 
but it had a high computation cost. The model was able to capture some of the anomalies but the performance was not the best. 

**Time Based Analysis**
The goal for this task was to choose one time-based column & analyze trends. I chose the Ad publishing date since it had no missing entries. But the downside was
this column only had around 40 unique observations. Thus, I had limitations in terms of algorithms I could use. I performed series decomposition & autocorrelation 
that revealed weekly seasonality. Finally, I created a model that would predict traffic for the next 7 days using random forest regression.
