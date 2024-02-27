# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/23004205/exno1/assets/138971114/2ec36b41-181a-47ed-9213-237b5d64ddeb)
```
print(df.head(7))
```
![image](https://github.com/23004205/exno1/assets/138971114/2fbf6d9a-bff1-4ec2-83ce-a11aaa039f09)
```
print(df.tail(2))
```
![image](https://github.com/23004205/exno1/assets/138971114/a988bdbd-1c2f-4ada-8fcc-6bb8a6047eff)
```
df.info()
```
![image](https://github.com/23004205/exno1/assets/138971114/8a8131a3-ad92-4df5-9811-3932051defc1)
```
print(df.describe())
```
![image](https://github.com/23004205/exno1/assets/138971114/26e8713c-ab01-4c75-bac7-e669ee6da980)
```
df.isnull().sum()
```
![image](https://github.com/23004205/exno1/assets/138971114/7a6f81d7-b8e3-434e-b2cb-f2a390b8dbe6)
```
df.nunique()
```
![image](https://github.com/23004205/exno1/assets/138971114/af916f5c-b79b-4d7a-b15e-8937e3617d8e)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/23004205/exno1/assets/138971114/47422bbb-b45b-450c-8eec-79361e0834ae)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/23004205/exno1/assets/138971114/80680dce-3f67-46d9-b7a2-4b430d430f48)
```
min=df.M4.min()
min
```
![image](https://github.com/23004205/exno1/assets/138971114/9992df49-1f2e-4bed-818a-760797c2845d)
```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/23004205/exno1/assets/138971114/3218c02e-1da2-469f-a0d1-485cc6fefb37)

![image](https://github.com/23004205/exno1/assets/138971114/e7e885e4-63be-4ca6-a9f9-bae1e3b92799)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![op1](https://github.com/23004205/exno1/assets/138971114/08588c9d-f8c7-40da-bf7a-267a32303e13)
```
sns.boxplot(data=af)
```
![op2](https://github.com/23004205/exno1/assets/138971114/643c099a-0cf8-4b80-8e46-1899ae2d0632)

```
sns.scatterplot(data=af)
```
![op3](https://github.com/23004205/exno1/assets/138971114/4ac41a9a-bb90-4dd3-8c08-538c92536862)
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![op4](https://github.com/23004205/exno1/assets/138971114/4358c9f1-ca3a-401d-a52e-f26bc767ce5e)
```
af=af[((af>=low)&(af<=high))]
af
```
![op5](https://github.com/23004205/exno1/assets/138971114/4c396f17-b505-4a38-b9d1-43da9cdf128f)
```
af.dropna()
```
![op6](https://github.com/23004205/exno1/assets/138971114/b4570b42-3c8c-4b1e-814b-d7955a94f796)
```
sns.boxplot(data=af)
```
![op7](https://github.com/23004205/exno1/assets/138971114/b456f34f-8c4e-43ab-95a1-9c1e5f7a6d5b)

```
sns.scatterplot(data=af)
```
![op8](https://github.com/23004205/exno1/assets/138971114/5a82771d-9a44-48df-9114-23cf347f2ec4)
```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![op9](https://github.com/23004205/exno1/assets/138971114/d4bcee07-e139-47bb-ac02-1d585e6b4990)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![op10](https://github.com/23004205/exno1/assets/138971114/d73126e3-ef16-4d36-88bd-33061778eb0a)

# Result
Thus the given program executed successfully.
