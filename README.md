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

# Data Cleaning:
```
import pandas as pd
a=pd.read_csv("/content/Data_set.csv")
a
```
![Screenshot 2024-08-22 110056](https://github.com/user-attachments/assets/04e33d88-1efd-4c34-9f87-4988f53f09f1)

```
a.isnull().sum()
```
![Screenshot 2024-08-22 110309](https://github.com/user-attachments/assets/a265b44a-9cbe-4714-af88-f11cad26345e)

```
df.isnull().any()

```

![Screenshot 2024-08-22 110426](https://github.com/user-attachments/assets/e576f45e-52c3-4bb6-8efb-aea7ddfe5fe6)

```
a.dropna()
```
![Screenshot 2024-08-22 110622](https://github.com/user-attachments/assets/98ded597-3e15-4e7f-a79f-eadb3729f460)

```
a.fillna(0)
```
![Screenshot 2024-08-22 110715](https://github.com/user-attachments/assets/43b7daca-cbbc-4aa3-8324-1cb7e56d9cdc)

```
a.fillna(method = 'ffill')
```
![Screenshot 2024-08-22 110838](https://github.com/user-attachments/assets/29e39955-ece9-4744-aa48-3aa4e05a3542)

```

a.fillna(method = 'bfill')
```
![Screenshot 2024-08-22 110950](https://github.com/user-attachments/assets/7ae129a8-4f90-45ec-96e6-5be06ad496ce)


```
a_dropped = a.dropna()
a_dropped
```

![Screenshot 2024-08-22 111100](https://github.com/user-attachments/assets/5feaad4a-0a83-4d38-91d8-58a85d9fc80e)

# IQR(Inter Quartile Range):
```
import pandas as pd
a=pd.read_csv("/content/iris.csv")
a
```
![Screenshot 2024-08-22 111529](https://github.com/user-attachments/assets/186915bf-0955-4f15-b4a3-9fc9fa60fea1)


```
a.describe()
```
![Screenshot 2024-08-22 111634](https://github.com/user-attachments/assets/80247d49-0509-4f00-a598-6c89109be920)


```
sns.boxplot(x='sepal_width',data=ir)
```
![Screenshot 2024-08-22 111803](https://github.com/user-attachments/assets/2b4cfd71-326c-4f19-a911-f1d3cd5bf892)

```
c1=a.sepal_width.quantile(0.25)
c3=a.sepal_width.quantile(0.75)
a=c3-c1
print(c3)
```
![Screenshot 2024-08-22 111929](https://github.com/user-attachments/assets/b910ae98-c778-48a9-9c29-15ac92984a9c)

```

rid=a[((a.sepal_width<(c1-1.5*iq))|(a.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```

![Screenshot 2024-08-22 112440](https://github.com/user-attachments/assets/5630ea44-e0a6-4f4d-bfa4-eb70c3221927)

```
delid=a[~((a.sepal_width<(c1-1.5*iq))|(a.sepal_width>(c3+1.5*iq)))]
delid

```

![Screenshot 2024-08-22 112514](https://github.com/user-attachments/assets/cb336669-f8c0-4726-a9a9-fb12ef8e7e7a)


```
sns.boxplot(x='sepal_width',data=delid)
```

![Screenshot 2024-08-22 112519](https://github.com/user-attachments/assets/f2c7526d-6d34-4d76-a698-e727ec9309c9)

# z-score:


```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("heights.csv")
dataset
```
![Screenshot 2024-08-22 113249](https://github.com/user-attachments/assets/e0741663-b725-4ed8-9551-1c5103198e51)

```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```
![Screenshot 2024-08-22 113334](https://github.com/user-attachments/assets/550b7b66-873b-455f-a22f-3451174067e5)

```
low = q1 - 1.5*iqr
low
```
![Screenshot 2024-08-22 113414](https://github.com/user-attachments/assets/9cf441dd-00c2-4cb1-bf75-dcd8f206f296)


# Result
        Hence the data was cleaned , outliers were detected and removed.
