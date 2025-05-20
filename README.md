# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program

## Program:
/*
Program to implement the K Means Clustering for Customer Segmentation.

Developed by: DINESH PRABHU S

RegisterNumber: 212224040077
*/
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv('Mall_Customers.csv')
data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])

KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![image](https://github.com/user-attachments/assets/7150789c-3107-4182-996e-d505c34b1cd1)

![image](https://github.com/user-attachments/assets/6558102a-824a-4598-9e80-0de38625d90d)

![image](https://github.com/user-attachments/assets/84237015-2c12-479d-a73e-f1b5ec4601ab)

![image](https://github.com/user-attachments/assets/052a8769-c84c-4104-8baa-d9f596ec1ff2)

![image](https://github.com/user-attachments/assets/04fdeadf-2d05-44f8-be9a-3d8567924959)

![image](https://github.com/user-attachments/assets/b128292e-0f50-45c3-b2a1-ce97dc1e8dfb)

![image](https://github.com/user-attachments/assets/4aac1fee-5d2c-4615-bde0-3a83d1e7c573)

![image](https://github.com/user-attachments/assets/26402cd9-bdb6-427b-8874-d47e95e687b9)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
