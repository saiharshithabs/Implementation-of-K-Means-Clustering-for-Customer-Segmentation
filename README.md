# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.mport the required packages.

2.Import the dataset to work on.

3.From sklearn module import kmeans.

4.Define number of clusters to be made.

5.Assign the cluster values.

6.Plot the cluster using matplotlib.pyplot

7.End the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: B S SAIHARSHITHA
RegisterNumber:  212220040139
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11): 
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

![image](https://github.com/saiharshithabs/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/eb3b99f4632c3458594a6a64e520d01450504e9b/WhatsApp%20Image%202022-11-10%20at%2009.08.20.jpg)

![image](https://github.com/saiharshithabs/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/ed74452dd0715567bcd0e826f323734802c24c70/WhatsApp%20Image%202022-11-10%20at%2009.13.34.jpg)

![image](https://github.com/saiharshithabs/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/3944e23c74d113844e64bb58cb61f1f2a2ec2f18/WhatsApp%20Image%202022-11-10%20at%2009.16.12.jpg)

![image](https://github.com/saiharshithabs/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/8d604b4bbcf6b8bda84a6532d4983341efe4894c/WhatsApp%20Image%202022-11-10%20at%2009.18.04.jpg)

![image](https://github.com/saiharshithabs/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/562536077f8f5b5dba1005a67e527c7d079fcc72/WhatsApp%20Image%202022-11-10%20at%2009.20.10.jpg)

![image](https://github.com/saiharshithabs/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/1a72de3d0c5dcc43ce29bae76e5352409d51e02b/WhatsApp%20Image%202022-11-10%20at%2009.22.44.jpg)

![image](https://github.com/saiharshithabs/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/d4a61d3467b8693b992ed0030d7f9ce7e50a70a2/WhatsApp%20Image%202022-11-10%20at%2009.26.51.jpg)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
