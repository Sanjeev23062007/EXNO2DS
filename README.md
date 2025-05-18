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
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```

![image](https://github.com/user-attachments/assets/57d2403a-ac02-4a52-a7f3-998b47222dd3)

```python
df.info()
```

![image](https://github.com/user-attachments/assets/45f39a69-bbc4-4e0e-93b6-ab8ecdce054d)

```python
df.shape
```

![image](https://github.com/user-attachments/assets/4a199900-8205-486f-9b20-7d2693b14dae)

```python
df.set_index("PassengerId",inplace=True)
df.describe()
```

![image](https://github.com/user-attachments/assets/c176f553-3c3b-4e91-ab5f-aaff5da38a22)

```python
df.shape
```

![image](https://github.com/user-attachments/assets/e4039b26-f761-4ea8-b51f-3f9450b8c618)

```python
df.nunique()
```

![image](https://github.com/user-attachments/assets/1cd701de-42fe-4f12-8ed4-2a6156c1dd8c)

```python
df["Survived"].value_counts()
```

![image](https://github.com/user-attachments/assets/a402822e-1868-4e21-8011-d61131ddc32f)

```python
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

![image](https://github.com/user-attachments/assets/f9883ae8-d4ad-488d-a1f4-c4db24e289ea)


```python
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/90f0d1b5-dbcb-4f01-b2e4-1cacbd6e9426)

```python
df
```

![image](https://github.com/user-attachments/assets/4e89bac9-83a8-415c-892c-5055d42f18f3)

```python
df.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/0036bbaa-babd-4ceb-bbe6-e102df009760)

```python
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

![image](https://github.com/user-attachments/assets/bdc2abf1-1afe-45d5-9b25-0491e354b2bd)

```python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/a7bd77e8-b274-4a51-82ce-baa2820bca48)

```python
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![image](https://github.com/user-attachments/assets/ab6f6026-c431-47c1-87d8-95acff948213)

```python
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/user-attachments/assets/25b7b944-8c81-43b8-be12-c14fcabab2cf)

```python
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/user-attachments/assets/8a463bcd-8f73-4b84-a940-e05bd1780304)

```python
sns.jointplot(x="Age",y="Fare",data=df)
```


```python
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/user-attachments/assets/6e52d49f-4b46-4445-8532-896a94f20813)

```python
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/02025dab-c66e-43f2-a74d-80fa8c6ab6fa)

```python
corr=df.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/user-attachments/assets/8782f51a-654e-42c3-9f75-7d7b2cd73989)

```python
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/daef3d3f-3108-4f2a-896b-f6121952d4dc)

# RESULT

We have performed Exploratory Data Analysis on the given data set successfully.
