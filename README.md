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
5.Print the outputs and end the program.
## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Shobika P
RegisterNumber:  212221230096

import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
![image](https://user-images.githubusercontent.com/94508142/204435220-1e6d062d-67d7-433b-984c-79ec469239fc.png)

![image](https://user-images.githubusercontent.com/94508142/204435269-11aa132c-aaf7-46b2-a1c9-e1ec5fe91ab7.png)
![image](https://user-images.githubusercontent.com/94508142/204435354-874683c6-dbc7-46ff-9140-f6b106af440a.png)
![image](https://user-images.githubusercontent.com/94508142/204435352-be87c5e2-806b-44f9-b902-c8aabd5560fe.png)
![image](https://user-images.githubusercontent.com/94508142/204435474-0a3d94c3-8879-412e-8d9a-71900412a6f6.png)
![image](https://user-images.githubusercontent.com/94508142/204435487-4e0eca63-11c0-47eb-8954-295c18a7084e.png)
![image](https://user-images.githubusercontent.com/94508142/204435526-5eeb7e08-ff29-4df0-9971-29bfc87fb075.png)
![image](https://user-images.githubusercontent.com/94508142/204435561-f8eaf97e-3b92-45f5-b7f2-6dcb429eef1a.png)
![image](https://user-images.githubusercontent.com/94508142/204435603-b290fa01-7ce9-4c2c-a5b7-77adba89dcfb.png)
![image](https://user-images.githubusercontent.com/94508142/204435643-5c19f7ee-c7a9-4839-8646-a13b54f9b2a2.png)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
