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
```

```
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1436" height="514" alt="image" src="https://github.com/user-attachments/assets/1a4db729-bab2-4b3d-882a-2d5cd40e02dc" />


```
df.info()
```
<img width="503" height="434" alt="image" src="https://github.com/user-attachments/assets/809cbcc7-b4b3-4952-9402-2e733fd23ea8" />



```
df.describe()
```
<img width="910" height="377" alt="image" src="https://github.com/user-attachments/assets/0bddfc34-3c06-4706-bc0c-d913c253c459" />



```
df.dtypes
```
<img width="298" height="563" alt="image" src="https://github.com/user-attachments/assets/f2fcaed8-b3d4-42ad-8c70-4a6305108e41" />


```
df.value_counts()
```
<img width="1559" height="607" alt="image" src="https://github.com/user-attachments/assets/dd736aa7-0813-4187-ada2-84442439f025" />



```
df['Age'].value_counts()
```
<img width="223" height="602" alt="image" src="https://github.com/user-attachments/assets/55dc86c8-e7ff-4c92-b213-790fb4cbb2bd" />



```
df.shape
```
<img width="136" height="40" alt="image" src="https://github.com/user-attachments/assets/0e434d4f-ca4f-45ee-9514-e89b9fb95401" />


```
df.set_index("PassengerId",inplace=True)
```
<img width="1455" height="561" alt="image" src="https://github.com/user-attachments/assets/ef6700ff-62b1-454e-9062-7dfb40102c8d" />

```
df.nunique()
```
<img width="192" height="524" alt="image" src="https://github.com/user-attachments/assets/9aeec463-d8c7-4fff-85ae-1ad60b9b7f6f" />



```
sns.countplot(data=df,x='Survived')
```
<img width="725" height="573" alt="image" src="https://github.com/user-attachments/assets/ac1d0643-9986-4c08-84ba-cd7c5a80cbe4" />


```
df.Pclass.unique()
```
<img width="189" height="46" alt="image" src="https://github.com/user-attachments/assets/2268e744-e285-49f7-9111-b7fa8fe66b47" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1434" height="569" alt="image" src="https://github.com/user-attachments/assets/26fa7c5f-a91b-4fc6-aac8-ce4dae2d2db0" />


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="941" height="652" alt="image" src="https://github.com/user-attachments/assets/b02954fb-3aef-4689-b2f1-6855d6c9d99d" />



```
df.boxplot(column="Age",by="Survived")
```
<img width="771" height="621" alt="image" src="https://github.com/user-attachments/assets/6a92fdd9-1f07-4f24-81e1-3f5c5207c36d" />




```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="744" height="580" alt="image" src="https://github.com/user-attachments/assets/6681d194-f6c5-427c-817c-f05f4fa2adf8" />



```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```


<img width="869" height="579" alt="image" src="https://github.com/user-attachments/assets/47938424-3646-4676-ab3d-eaca8058aeb5" />





```
plt=sns.boxplot(x="Pclass",y="Age",hue='Gender',data=df)
```
<img width="775" height="559" alt="image" src="https://github.com/user-attachments/assets/0dc96a4e-efa4-4dd2-bfe8-01e97f9e2db7" />


```
import seaborn as sns
sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="1440" height="665" alt="image" src="https://github.com/user-attachments/assets/019bf886-4c31-480f-bfc6-9627c6a8fa8f" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1389" height="652" alt="image" src="https://github.com/user-attachments/assets/ea8dbbd1-0792-4a15-a015-d9618dab57ab" />




```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="705" height="566" alt="image" src="https://github.com/user-attachments/assets/bace2a90-6614-45a0-9da3-d560a7b22eb9" />




```
corr=df.corr(numeric_only=True)
sns.heatmap(corr)
```
<img width="759" height="567" alt="image" src="https://github.com/user-attachments/assets/c0a82263-99a0-46c1-b179-75a02466b694" />




# RESULT
       The output has verified successfully
