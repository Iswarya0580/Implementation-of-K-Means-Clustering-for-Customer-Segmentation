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
Developed by: Iswarya P
RegisterNumber:  212223230082
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("C:/Users/Manju Mageswari/OneDrive/Desktop/Ishu/ml/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

```km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:

## Elbow method:
![Screenshot 2024-09-30 110344](https://github.com/user-attachments/assets/5d563c3f-fbe5-4b1b-a001-7811143ac833)

## Y_Pred:
![Screenshot 2024-09-30 110351](https://github.com/user-attachments/assets/d32c6873-ba54-45bd-ba15-c313d7a7ae6a)

## Customer Segments:
![Screenshot 2024-09-30 110403](https://github.com/user-attachments/assets/8c70e8af-7f2e-489e-b7d3-f642d8e47e00)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
