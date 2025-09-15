# EXP NO 2
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
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1485" height="906" alt="Screenshot 2025-09-15 113006" src="https://github.com/user-attachments/assets/07a861fe-d663-43a2-b82d-79261607d8b8" />


```
df.info()
```
<img width="513" height="513" alt="Screenshot 2025-09-15 113017" src="https://github.com/user-attachments/assets/f59cb8b7-1da0-4607-8ed0-314d33f5dcd8" />


```
df.describe()
```
<img width="911" height="443" alt="Screenshot 2025-09-15 113030" src="https://github.com/user-attachments/assets/78abaf23-4db8-4ca0-8dd7-4502fe8972d0" />


```
df.dtypes
```
<img width="443" height="631" alt="Screenshot 2025-09-15 113037" src="https://github.com/user-attachments/assets/22fb8a33-18e0-45ae-998f-0bc9ab4c49b2" />


```
df.shape
```

<img width="270" height="105" alt="Screenshot 2025-09-15 113045" src="https://github.com/user-attachments/assets/946e19cc-57dc-46b5-b818-d935fcdb7de0" />

```
df.value_counts()
```
<img width="1474" height="789" alt="Screenshot 2025-09-15 113113" src="https://github.com/user-attachments/assets/cbde712b-ed9b-401c-a2f0-afa519fe6bae" />


```
df['Age'].value_counts()
```
<img width="462" height="707" alt="Screenshot 2025-09-15 113121" src="https://github.com/user-attachments/assets/4196d607-6b99-4b61-b40f-52f9943038bd" />


```

df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
<img width="1411" height="698" alt="Screenshot 2025-09-15 113136" src="https://github.com/user-attachments/assets/eb98a48a-2c54-42af-b399-95b33b7b5a0d" />


```
df.nunique()
```

<img width="461" height="607" alt="Screenshot 2025-09-15 113150" src="https://github.com/user-attachments/assets/c6d7e238-a785-4f77-92d9-b79704a19313" />

```
sns.countplot(x=df['age'])
```
<img width="916" height="652" alt="Screenshot 2025-09-15 113202" src="https://github.com/user-attachments/assets/79f71e76-5a7c-49cf-9bd0-0be395c97407" />


```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
<img width="1462" height="769" alt="Screenshot 2025-09-15 113224" src="https://github.com/user-attachments/assets/3f500243-81e6-43d9-be6d-e45bc01ff83e" />


```

sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```



```
df.boxplot(column='Age',by="Gender")
```
<img width="922" height="678" alt="Screenshot 2025-09-15 113334" src="https://github.com/user-attachments/assets/a9cf6599-36f3-450c-bd36-e63b6ba4374e" />


```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
<img width="962" height="651" alt="Screenshot 2025-09-15 113345" src="https://github.com/user-attachments/assets/2513e352-9964-4e0e-82f3-4fa37f2af5ca" />

```

pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
<img width="893" height="625" alt="Screenshot 2025-09-15 113354" src="https://github.com/user-attachments/assets/a4416419-20b3-45a4-b85d-563313ebf82a" />


```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
<img width="1480" height="715" alt="Screenshot 2025-09-15 113407" src="https://github.com/user-attachments/assets/94976606-a5bd-46a5-8cd4-426d94bf1161" />


```
corr=df.corr(numeric_only)
sns.heatmap(corr,annot=True)
```

<img width="848" height="662" alt="Screenshot 2025-09-15 113415" src="https://github.com/user-attachments/assets/03a43e37-3d5f-416b-9715-d5abd71f5c5a" />



# RESULT
     Code are sucessfully executed.
