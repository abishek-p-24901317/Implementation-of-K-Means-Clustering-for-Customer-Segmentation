# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load & inspect data: Read the Mall_Customers.csv file into a DataFrame, view column types and check for missing values to ensure the dataset is clean.
2. Determine optimal k (Elbow method): For k from 1 to 10, fit a K-Means model on the two numeric features Annual Income and Spending Score, record the within-cluster-sum-of-squares (WCSS), and plot WCSS vs. k to spot the “elbow” where adding clusters yields diminishing returns.
3. Train final model & label data: Choose k = 5 (from the elbow), train K-Means, predict each customer’s cluster, and append the resulting labels to the DataFrame as a new cluster column.
4. Visualize segments: Split the DataFrame by cluster label and create a scatter plot of Annual Income vs. Spending Score, coloring each cluster differently and adding a legend to clearly show the five customer segments.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Abishek P
RegisterNumber:  212224240002

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans = KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data['cluster']=y_pred
df0=data[data['cluster']==0]
df1=data[data['cluster']==1]
df2=data[data['cluster']==2]
df3=data[data['cluster']==3]
df4=data[data['cluster']==4]
plt.scatter(df0['Annual Income (k$)'],df0['Spending Score (1-100)'],c="red",label='cluster0')
plt.scatter(df1['Annual Income (k$)'],df1['Spending Score (1-100)'],c="black",label='cluster1')
plt.scatter(df2['Annual Income (k$)'],df2['Spending Score (1-100)'],c="blue",label='cluster2')
plt.scatter(df3['Annual Income (k$)'],df3['Spending Score (1-100)'],c="green",label='cluster3')
plt.scatter(df4['Annual Income (k$)'],df4['Spending Score (1-100)'],c="magenta",label='cluster4')
plt.legend()
plt.title("Customer Segments")
*/
```

## Output:
## Data head:
![image](https://github.com/user-attachments/assets/88e10fdb-799a-4efe-ac2d-16576f8143f5)
## Data info:
![image](https://github.com/user-attachments/assets/d276da50-993d-40aa-a147-9de8212849b7)
## check for null:
![image](https://github.com/user-attachments/assets/bcee578c-ff94-4319-9bd5-a2947ce8b256)
## Elbow Method:
![image](https://github.com/user-attachments/assets/9c9c39df-96d6-4f1a-89e4-a8003c00e99d)
## Kmeans:
![image](https://github.com/user-attachments/assets/c6d90d04-7f2a-4517-ba26-539d8cf8c78e)
## y_predicted:
![image](https://github.com/user-attachments/assets/076d9bd7-21e7-435a-94e2-c8869228c728)
## Customer Segments:
![image](https://github.com/user-attachments/assets/9037b0c3-a760-4980-93f7-c79d616aa8d3)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
