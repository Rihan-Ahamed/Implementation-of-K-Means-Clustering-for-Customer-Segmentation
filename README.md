# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Start
2. Import the necessary packages using import statement.
3. Read the given csv file
4. Import KMeans and use for loop to cluster the data.
5. Predict the cluster and plot data graphs.
6. End

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Rihan Ahamed S
RegisterNumber:  212224040276

```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]   #Within-Cluster Sum of Squares.

for i in range(1,11):
    kmeans=KMeans(n_clusters=i, init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
    
plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("ELBOW METHOD GRAPH")
plt.show()
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="green",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="purple",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="gold",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
## df.head():

<img width="786" height="296" alt="331335569-6bfe56ab-cb96-410a-9db4-f55e7e43505e" src="https://github.com/user-attachments/assets/f0b84f39-254e-4ea9-af8f-3d45fc0babca" />

## df.info():

<img width="757" height="295" alt="331335724-26e99a9b-155e-48f9-a406-202c4f0c1424" src="https://github.com/user-attachments/assets/43e50060-8d26-44a3-b3d5-30da6097bea7" />

## df.isnull.sum():

<img width="596" height="200" alt="331335777-04b7dfd0-ff27-41d3-90db-dad7be88b8ad" src="https://github.com/user-attachments/assets/673a7543-1572-4e80-ad16-2fdb8c695499" />

## Elbow method:

<img width="1024" height="723" alt="371960375-5d563c3f-fbe5-4b1b-a001-7811143ac833" src="https://github.com/user-attachments/assets/c14281af-899a-48f8-9fd7-31fa17c4eeca" />

## Y_Pred:

<img width="866" height="311" alt="371960377-d32c6873-ba54-45bd-ba15-c313d7a7ae6a" src="https://github.com/user-attachments/assets/7cd5de03-5e89-4c6d-aaa0-b3d66dd529c9" />

## Customer Segments:

<img width="883" height="702" alt="371960376-8c70e8af-7f2e-489e-b7d3-f642d8e47e00" src="https://github.com/user-attachments/assets/28a69373-306f-4196-877f-bf95ee7665a0" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
