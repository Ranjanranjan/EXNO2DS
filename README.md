# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![Screenshot 2024-04-01 134113](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/8959f731-c8d7-41d2-8867-39f01f3dc81c)



```
dt.info()
```
![Screenshot 2024-04-01 134138](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/02a38f08-c242-4769-9a53-63bc4f329605)



```
dt.shape
```
![Screenshot 2024-04-01 134148](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/7a3e7429-ac4b-4b93-911c-0f564f0fe24b)



```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![Screenshot 2024-04-01 134201](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/b9cbeb4b-87d9-465d-9057-214751b229ea)



```
dt.nunique()
```
![Screenshot 2024-04-01 134209](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/7d4fa248-e835-4d3b-b04a-6e98ed11b11c)



```
dt["Survived"].value_counts()
```
![Screenshot 2024-04-01 134217](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/9656374c-f604-4252-9281-2c848d7b421a)


```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2024-04-01 134228](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/e8702307-b228-4e2b-a56b-8384f41f4922)



```
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2024-04-01 134238](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/0641e7b6-496a-4e62-a892-2a01198bff60)


```
dt
```
![Screenshot 2024-04-01 134248](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/907ad797-790d-4101-95e0-3f2309797b0f)



```
dt.Pclass.unique()
```
![Screenshot 2024-04-01 134254](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/f6b13c73-a1eb-4f5f-9084-aebf55b45178)



```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![Screenshot 2024-04-01 134304](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/251cf089-b136-4371-9b5d-98de381e2f77)



```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![Screenshot 2024-04-01 134317](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/59826f4d-dfeb-4c85-885c-aecf27633a2f)



```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
![Screenshot 2024-04-01 134331](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/23e0d32b-6137-4727-a1ae-d28188fab62b)



```
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-04-01 134346](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/a2eccdb3-7258-4490-a79a-b54d49fb1313)



```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2024-04-01 134355](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/2ea0edd5-ab79-4451-9913-51f17a3720a5)



```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2024-04-01 134414](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/db7d1fe7-55d4-47eb-98fb-f70c120b2181)


```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![Screenshot 2024-04-01 134425](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/2a9f4048-db8a-42cd-83d3-82216b75fb13)


```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2024-04-01 134438](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/791b35a9-58d5-493e-95e7-0714206facba)



```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2024-04-01 134448](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/4a97c226-c264-479c-b964-69cb47056af1)


```
sns.pairplot(dt)
```
![Screenshot 2024-04-01 134501](https://github.com/Ranjanranjan/EXNO2DS/assets/130027697/156141bd-3ccc-4d55-a993-b1e223c8e122)



        
# RESULT
        Thus, the Exploratory Data Analysis on the given data set was performed successfully. 
