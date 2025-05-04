# SOMs and K-Means Clustering: Assessing Atmospheric Blocking Event Patterns Through Machine Learning

## Introduction to Additional Testing with K-Means and Its Application

K-Means clustering is a commonly used unsupervised learning algorithm designed to
partition data into _k_ distinct groups based on feature similarity. It works by minimizing
the variance within each cluster, iteratively updating cluster centroids until convergence.
In meteorology, k-means can be used to classify large-scale circulation regimes, identify
recurrent synoptic patterns, and detect spatial variability in many feilds; in our case,
potential vorticity and geopotential height. The simplicity, speed, and interpretability in 
k-means makes it a useful tool to explore pattern recognition. When applied to image-based
data, k-means can help uncover dominant flow regimes- including blocking patterns-
without requiring subjective thresholds. While it lacks the spatial preservation of 
self-organizing maps (SOMs), k-means can provide an objective reference for clustering
performance, aid in determining the number of distinct circulation types, and guide
further anallysis usiing more specialiizeed tools such as SOMs.

## Methods with K-Means

In addition to SOMs, we applied k-means clustering as a complementaray method for 
objectively classing blocking patterns. Utilizing ERA5 data, k-mean was applied to 500 hPa
geopotential height and PV fields, first using raw pixel representations off image data and 
later using features extraacted from a pre-traained convlutional neural network (CNN). 
Evaluation metrics such as Silhouette Score, Callinski-Harabasz Index, and Davies-Bouldin
Index were used to assess clustering performance. Dimensionally reduced techniques like
t-SNE were employed for visual inspection of cluster seperation. Whille SOMs are better
suited for preserving spatial relationships and mapping non-linea features, k-means provides
a fast, interpretable baseline that can help SOM node initialization, guide hyperparameter
tuning, or servee as a benchmark for comparing classification outcomes.

## Discussion

The k-means clustering results revealed several coherent circulation regimes across the 
90-day summer composites. Clustering associated with strong mid-tropospheric ridging,
closed geopotential height contours, and PV gradients were visually and dynamically 
consistent with atmospheric blocking features. Although the Silhouette Scores were low,
the use of CNN-extracted features yieled more structured and meteorologically meaningful
groupings than raw pixel imputs. Clusters with persistent high-pressure anomalies
and weak zonal flow likely corresponded to blocking events. These findings demonstrate
that k-means, when paired with feature engineering and visual validation, can successfully
isolate blocking-like states.

Importantly, the patterns identified through k-means clustering can complement SOM-based
classification by providing an independent grouping of the same atmospheric states. K-means
results can inform SOMs configuration decisions- such as the optimal number of nodes- and
help evaluate the stability of identified patterns. Moreover, convergence between the two
methods strengthens confidence that the extracted clusters represent physically meaningful
regimes. By integrating k-means into the analysis, we add another additional layer of 
validation that supports the identification of persistent, high-impact atmospheric patters.
