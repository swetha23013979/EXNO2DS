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

## PROGRAM
```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/0fd4762a-edf1-465b-a9fa-fd431a2add0f)

```
df.dropna(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/e4c5368c-0084-43f8-b269-c50f2aa97b90)

```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/8b56d75f-8bb5-4ceb-aaef-8fb83238eb28)

```
df.info()
```
![image](https://github.com/user-attachments/assets/88079c11-96cd-460e-9149-a26f85e79765)

```
df.shape
```
![image](https://github.com/user-attachments/assets/9ca14062-150f-40b7-b461-ff1234ffab2d)

```
df.set_index("PassengerId",inplace=True)
```
![image](https://github.com/user-attachments/assets/0582b8f1-ec95-45d9-b118-ca32f5205ebf)

```
df
```
![image](https://github.com/user-attachments/assets/ac3348d9-9b7a-4fcf-98ce-8edd29278ecc)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/4710723a-75db-41b3-b322-216378d45946)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/ceb3b52c-0f06-44ff-a12f-dc4b507f4342)

```
ms=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
ms
```
![image](https://github.com/user-attachments/assets/ff3d562f-8ca8-417f-abd7-0a661d890807)

```
import matplotlib.pyplot as plt
import seaborn as sns
sns.countplot(data=df,x="Sex")
```
![image](https://github.com/user-attachments/assets/13358c14-a20e-4af3-bf5e-a5b98b101f5c)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/5277a6f3-822e-40be-927f-b6d93ccf2830)

```
df.rename(columns = {'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/b60c55e4-9fc3-423c-8068-3828b1cc1f09)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5, aspect=.7)
```
![image](https://github.com/user-attachments/assets/dc47068b-6da9-454e-9bc8-74f99bfbd315)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/e278dd47-aba0-4586-a686-9ff8504659e0)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/89a2816a-5ff7-4642-8b0a-9c1be64d64a7)
```
```

# RESULT
       Thus we have cleaned the data and removed the outliers by detection using IQR method.
