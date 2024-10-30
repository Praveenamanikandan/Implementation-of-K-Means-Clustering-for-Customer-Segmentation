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


```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRAVEENA M
RegisterNumber:  212223040153
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
```

## Output:

![image](https://github.com/user-attachments/assets/1d7ae9b7-2dd6-45c8-891f-7bfdea3ca150)


```

data.info()
```

## Output:
![image](https://github.com/user-attachments/assets/5416b656-eed8-4c85-a076-46edf819fcf4)


```

data.isnull().sum()

```
## Output:

![image](https://github.com/user-attachments/assets/5773f727-c0da-4ed9-998a-e047b651ec46)

```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans (n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plot.xlabel("no of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")


```


## Output:
![image](https://github.com/user-attachments/assets/0e3fa62b-99ad-4c38-b99b-dcd7a828d6d6)


```

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
```

## Output:
![image](https://github.com/user-attachments/assets/0036d59c-e311-40ce-a8e0-c56d5c3b3ac2)

```
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```


## Output:


![image](https://github.com/user-attachments/assets/ef54bcc5-6984-4a31-805a-abf913a5b30e)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
