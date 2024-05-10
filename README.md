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
![324753751-f9c52b29-674b-475e-a317-7f717494c4d2](https://github.com/Swetha733N/EXNO2DS/assets/122199934/f5c912c7-b9b8-42d3-a540-78a062359467)

```
dt.info()
```
![324754033-806a43c9-dbf7-4337-a76d-eb26133ce1d8](https://github.com/Swetha733N/EXNO2DS/assets/122199934/41c7965d-64a3-46be-840e-59cca8e1eb90)

```
dt.shape
dt.head(4)
dt.tail(4)
dt.set_index("PassengerId",inplace=True)
```
![324755704-782b770c-6a48-4102-8ef1-087fd853418d](https://github.com/Swetha733N/EXNO2DS/assets/122199934/3bcbdfe6-ec7d-4762-9f6b-411b72a78485)

```
dt.describe()
dt.nunique()
dt["Survived"].value_counts()
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![324756089-45d05238-a279-412b-9d5e-dd2c64b5fdc9](https://github.com/Swetha733N/EXNO2DS/assets/122199934/e700aaf5-6fd1-4f97-945f-8ed68186e5df)

```
sns.countplot(data=dt,x="Survived")
dt
dt.Pclass.unique()
dt.rename(columns = {"Sex":"Gender"},inplace = True)
dt
```
![327724610-29cdec7c-9c4e-4a9c-866b-15d1d7817a0a](https://github.com/Swetha733N/EXNO2DS/assets/122199934/17d9e2f8-9714-4ac6-8bef-5941d824b59e)
![327724626-5223d5af-86bc-42b8-be53-4642074a4df2](https://github.com/Swetha733N/EXNO2DS/assets/122199934/8c591c4c-7518-4c89-970c-8f0e9dea59ff)
![327724636-dd16d9ed-cda3-45d7-a17c-438b5f703e04](https://github.com/Swetha733N/EXNO2DS/assets/122199934/3269a762-dc6a-49f9-b1eb-a51904a950a2)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![327725510-e355a7e6-28db-4417-92c9-60ca3a868925](https://github.com/Swetha733N/EXNO2DS/assets/122199934/07501816-24d3-425b-997a-8a668dbd70b9)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![327725524-3c7ce365-3736-4066-9a72-4c6bb907dbeb](https://github.com/Swetha733N/EXNO2DS/assets/122199934/c7d4d9e9-afc3-4f01-abae-d8b6ab3a449b)


```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![327725540-9e8f2261-8290-44be-9e6b-ec116561326b](https://github.com/Swetha733N/EXNO2DS/assets/122199934/47dfe0c7-46f8-4752-99d7-c0e8e3669396)

```
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x="Pclass",y='Age',hue='Gender',data=dt)
```
![327725557-c1fb126f-b73a-49d6-9e5f-8cc2ad6f3f5f](https://github.com/Swetha733N/EXNO2DS/assets/122199934/e92bf118-113b-4dd1-ab6b-f5c8e46371c3)


```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![327725570-eb6d5f15-c3b3-4c88-a4ef-abfe07b009e4](https://github.com/Swetha733N/EXNO2DS/assets/122199934/463230db-ff14-49df-9a07-47e6b411441a)


```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![327725586-2ebef9a2-7e58-4e77-81ac-2d65d3eb03af](https://github.com/Swetha733N/EXNO2DS/assets/122199934/03b4dfd7-d71e-42ff-bad8-e81be49b5f22)


```
sns.pairplot(dt)
```

![327725614-32cac6cc-7397-4215-8575-484e3643b9fb](https://github.com/Swetha733N/EXNO2DS/assets/122199934/30212f68-4eb3-4ff2-9c97-23c4f0e2245f)

# RESULT
      Thus, Exploratory Data Analysis for the given dataset is done successfully.
