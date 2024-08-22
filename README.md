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
df=pd.read_csv("SAMPLEIDS.csv")
df
```
![image](https://github.com/user-attachments/assets/e7f408be-e86a-4e97-b59d-7b9af05e7c38)

```
df.head()
```
![image](https://github.com/user-attachments/assets/76afc721-93aa-451e-8e8f-47c842a0ccf4)

```
df.tail()
```
![image](https://github.com/user-attachments/assets/bef7b4a2-6740-467d-ac7c-deec843af88d)


```
df.isnull()
```
![image](https://github.com/user-attachments/assets/8a436e9c-0296-465e-b87c-b99c6a44f567)

```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/c6efead1-f5c2-4c9c-9b90-9a8344b70cb1)

```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/66dabfa6-bc38-4f03-ae4f-3af2de99fb81)

```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/70b64f4e-cbb1-4dfc-bae6-b0ceb1ef0eaa)

```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/9a97d21d-6aed-4dbf-a97a-2c264b460509)

```
df.fillna(method = 'ffill')
```
![image](https://github.com/user-attachments/assets/bdc94f74-10e2-4c11-844a-cf4119c3b69b)

```
df.fillna(method = 'bfill')
```
![image](https://github.com/user-attachments/assets/9c5d456b-3c84-4da4-bb16-17d89f0c6e44)

```
df_dropped = df.dropna()
df_dropped
```
![image](https://github.com/user-attachments/assets/26e95107-fd13-4daf-85fc-582775a834ec)

```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![image](https://github.com/user-attachments/assets/6ef06c75-247a-4be1-977d-de3720e22c37)

```
import pandas as pd
ir=pd.read_csv('iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/5acccbbd-c05b-44c5-b6ce-f711ba32397b)

```
ir.describe()
```
![image](https://github.com/user-attachments/assets/fbe17407-c3cc-4111-a027-6cbdd7e86908)

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/7195a1cb-a28d-40f3-99ce-29856429040c)

```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![image](https://github.com/user-attachments/assets/79e60c90-7d98-4528-952d-fbd825ff56bc)

```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/302756ef-645f-444e-80d7-963a21607473)

```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![image](https://github.com/user-attachments/assets/fcc9e349-ab55-4537-a1c5-31f8c65268c4)

```
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/bfa57004-fa0f-43bd-a94d-241400119cf4)

```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
```
```
dataset=pd.read_csv("heights.csv")
dataset
```
![image](https://github.com/user-attachments/assets/7ea9c89f-f83a-4e0f-9305-24f122d1b53b)

```
z = np.abs(stats.zscore(dataset['height']))
z
```

![image](https://github.com/user-attachments/assets/d27b566c-e3fd-4ff8-bea6-67ed32510fb0)



# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
