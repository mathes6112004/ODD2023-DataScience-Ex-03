# ODD2023-DataScience-Ex-03
# Ex03-Univariate-Analysis
## Aim:To read the given data and perform the univariate analysis with different types of plots.

## Explanation:Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

## Algorithm :
### Step1
Read the given data.
### Step2
Get the information about the data.
### Step3
Remove the null values from the data.
### Step4
Mention the datatypes from the data.
### Step5
Count the values from the data.
### Step6
Do plots like boxplots,countplot,distribution plot,histogram plot.

# Program:
```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

```
from google.colab import files
uploaded = files.upload()
```

```
df = pd.read_csv('diabetes.csv')
df
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/130a312e-9497-4834-b887-a05cdf54f7b0)

```
df.isnull().sum()
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/31813012-86f8-4163-afbd-7aabb79e9f42)

```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/29990d67-8354-45f0-9470-c6388dcae1c8)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/3bfd7985-d8c7-4bde-abb9-3f27eedd8995)

```
sns.boxplot(df)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/c47fbd9b-05c4-4d32-8d91-885039d73568)

```
sns.displot(x ="Glucose", data = df)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/337bb8bd-0815-40a8-b048-54229b1cf126)

```
sns.displot(x ="BloodPressure", data = df)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/63e6ae17-cf7b-4053-a5f1-022266300f1f)

```
sns.displot(x ="BMI", data = df)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/07abe57d-e723-42b5-8026-8b4ea6a8fca6)

```
sns.displot(x ="DiabetesPedigreeFunction", data = df)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/20fb4b20-fa0e-4350-b871-d0d78f4fa3d5)

```
sns.displot(x ="Age", data = df)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/22128721-148b-42b2-b698-180c6cb32597)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/f90a054f-4a70-49bf-9f21-a94f378e71ca)

```
df = pd.read_csv('employeesal.csv')
df
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/86dfe8db-e3d8-40b5-81b7-8bdb2db1a160)

```
df.isnull().sum()
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/3b3728a1-6d78-43c5-ad93-43b8f49ef0c8)

```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/a6869720-2d0f-4d77-8395-76ed0147e90f)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/99292a84-ea92-460a-833d-947a6c7a88a2)

```
sns.boxplot(numeric_cols)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/fdb0ab9d-50c4-47ff-a623-6af911d9482b)

```
sns.histplot(x = 'Experience_Years',data = numeric_cols)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/129bd710-4ace-46f6-af28-97640b708500)

```
sns.histplot(x = 'Age',data = numeric_cols)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/402bc1e7-370d-4860-8394-3203681d4eb6)

```
sns.histplot(x = 'Salary',data = numeric_cols)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/80929ec0-e544-42e9-94a7-15581a46f444)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/8a60b7cc-23ae-4846-aece-8c03d8fb82da)

```
df = pd.read_csv('SuperStore.csv')
df
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/64c69d00-b2e8-47c1-a4a4-4fd0ca80c22a)

```
df.isnull().sum()
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/5f1d1fc7-6ac7-4a75-bb3a-419c9e436e96)

```
df.dropna()
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/e8a35ed4-fb79-4427-b6ef-83b121ac4044)

```
df.dtypes
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/2e07fb98-221c-4630-a3cd-8a6add748e12)

```
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/75080736-b6b5-4c01-a2fc-aa94930405c8)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
```
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/2c38555a-47cc-422f-ba34-ee0301826a04)

```
sns.histplot(x = 'Sales',data = numeric_cols)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/83b2436b-11c3-4f58-90f1-ae08b81971e8)

```
sns.countplot(x="Postal Code", data=numeric_cols)
```
![image](https://github.com/mathes6112004/ODD2023-DataScience-Ex-03/assets/119477782/3544dcd1-fe26-4162-81f1-c36d89e974cd)

# RESULT:
Thus we have read the given data and performed the univariate analysis with different types of plots.























