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
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/07667221-debd-48ae-85b4-6110ae4db4b2)

```
dt.info()
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/fa922d00-1dbb-4e10-8f76-366b81d50246)

```
dt.shape
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/c1d1a9c3-e1f6-4a8c-a503-9e8657aed25b)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/8081fa48-1c8b-4e75-a8b5-18d670d410a9)
```
dt.nunique()
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/76017b50-3949-4ad3-8ef3-bf7cdf6a6cda)

```
dt["Survived"].value_counts()
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/90a4741e-ce2e-4977-8885-2f726868b2f8)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/d498dfc3-8c2c-4a2b-8e60-d9c30d3c22eb)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/76c80e5d-581a-4a39-b8fa-a030f99d7555)

```
dt
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/74178392-d633-4773-858e-c7860cb91434)

```
dt.Pclass.unique()
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/e6ef4585-ca51-402c-8bb0-428badd8ed4f)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/33f662ec-4ed9-49b9-83e0-f37a3800e952)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/1bb2d3e8-4251-4fe5-af47-92c15036b53e)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/64ffad15-350e-4462-baed-76468b3b041c)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/f9ac9ea9-3ee0-4b22-8ede-7f6f03426b8c)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/30e45b8b-468e-4913-8bb9-cac7a678b494)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/2d189cf9-44dc-4dba-8fcd-317967174e1d)

```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/6ca21d1d-7582-418c-9c9e-224bea8e638a)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/56a59ea5-3483-40e5-8cd6-d5671af2d8ac)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/b18cd762-efde-4737-a11d-7fa683d9886a)


```
sns.pairplot(dt)
```
![image](https://github.com/Sangavi-suresh/EX-02-DS/assets/118541861/c9f23aaf-4ff4-49e7-b757-b54376bad427)



# RESULT
  
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
