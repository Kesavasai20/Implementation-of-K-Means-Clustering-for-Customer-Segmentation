# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program
## Program:
## Program to implement the K Means Clustering for Customer Segmentation.
## Developed by: K KESAVA SAI
## RegisterNumber: 212223230105 
```PY
'''
Program to implement the K Means Clustering for Customer Segmentation.
Developed by : K MADHAVA REDDY
RegisterNumber : 212223240064  
'''
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r'Mall_Customers.csv')

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
plt.title("Customer Segments")
```

## Output:
## Head():
![image](https://github.com/Kesavasai20/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849303/0f48d1f9-eab8-4df1-b9c7-ffec24313325)
## Info():
![image](https://github.com/Kesavasai20/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849303/2bf4ff7b-953e-4cf0-9e1d-0a57a3ac2282)
## isnull.sum():
![image](https://github.com/Kesavasai20/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849303/ee0a12f6-43a2-43bb-9ec0-7f1d8f6c3383)
## Elbow Method:
![image](https://github.com/Kesavasai20/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849303/4bb99fac-c856-48f3-b822-ffcdf92ba1e1)
## Fitting the no. of clusters:
![image](https://github.com/Kesavasai20/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849303/78c9faf7-cdd3-4980-bc7c-c72942c027fc)
## Prediction of Y:
![image](https://github.com/Kesavasai20/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849303/5a6a2722-834e-4212-994d-5751a3c1432c)
## Customer Segments:
![image](https://github.com/Kesavasai20/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849303/d8cbb81e-2623-4337-88ea-43ea67662e00)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
