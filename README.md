# Take-Home-Project-Repo
This repo hosts notebooks for the Definity's Take-Home Project of Poland cars for sale dataset.

The Dataset hosts Ads posted between March 2021 to May 2021 for majority of the cars in Poland but also 
from the other regions as well. The dataset is mostly clean with some of the columns having missing entries. 

We perfomed 3 tasks on the dataset. Here are approach & findings from each of them

**Vehicle Segmentation:**
The goal of this task is to segment or group vehicles having similar characteristics. For this task, after doing basic EDA we found out 
that data has some outliers & missing values. We needed to do imputation & scaling to make data cleaner & have same scale since the features
had varying scale. We experimented with KMeans & GMM. Utilizing KMeans helped us to group cars with similar price, engine power & age to cluster
together while GMM highlighted cars with anomalous characteristics.

GMM was better as spotting anomalies since it's probabilistic approach as doesn't assume spherical clusters. Thus it's good with clusters
with lots of overlaps.

**Anomaly Detection:**
The goal for this task was to spot anomalies in data. The challenge here was 50% of columns indicating vehicle properites had large chunk of data missing. To 
tackle this we used group imputation. For modelling we use isolation forest owinng to high dimentionality of our data & less computation cost. We tried DBSCAN 
but it had high computation cost. The model was able to capture some of the anomalies but the performance was not the best. 

**Time Based Analysis**
The goal for this task was to choose one time based column & analyze trends. We chose Ad publishing date since it has no missing entries. But the downside was
this column only had around 40 unique observations. Thus we had limitations in terms of algorithms we could use. We performed series decomposition & autocorrelation 
that revealed weekly seasonlity. Finally, we created model that would predict traffic for next 7 days using random forest regression.



