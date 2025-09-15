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
print(df)
```
<img width="867" height="732" alt="image" src="https://github.com/user-attachments/assets/17677452-943b-4992-ba0c-770d2c9957cd" />
```
df.head()
```

<img width="1167" height="263" alt="image" src="https://github.com/user-attachments/assets/76fbc3b7-0b06-4b98-a08b-36e9fcbecad8" />
```
df.tail()
```
<img width="1132" height="246" alt="image" src="https://github.com/user-attachments/assets/999a6cf7-21ff-44ff-ada8-7ba13fa0efa7" />
```
df.isnull()
```

<img width="961" height="707" alt="image" src="https://github.com/user-attachments/assets/cc3c8aa1-4064-4f6a-9029-2bbb959ee8ec" />
```
df.isnull().sum()
```

<img width="467" height="576" alt="image" src="https://github.com/user-attachments/assets/f8141c40-1173-46d1-9fef-a28cb6af404d" />
```
df.isnull().any()
```

<img width="372" height="563" alt="image" src="https://github.com/user-attachments/assets/10d0b486-3aec-4ab1-92ef-feda16f78846" />
```
df.dropna()
```

<img width="1151" height="565" alt="image" src="https://github.com/user-attachments/assets/eca32b05-449b-4dd8-8985-8ba6c29a5615" />
```
df.dropna(axis=0)
```

<img width="1111" height="565" alt="image" src="https://github.com/user-attachments/assets/7a97bbf7-d9ac-465f-93e1-ff4ea68ae315" />
```
df.dropna(axis=1)
```

<img width="566" height="712" alt="image" src="https://github.com/user-attachments/assets/3eb4f6d0-b702-4710-8adb-f206d48b47bd" />
```
df.fillna(0)
```

<img width="1115" height="706" alt="image" src="https://github.com/user-attachments/assets/0fbddfb8-5d5a-400e-9b15-de5b6f9b191c" />
```
df.fillna(method='ffill')
```

<img width="1155" height="728" alt="image" src="https://github.com/user-attachments/assets/8b919fff-46f3-42d0-9b19-b0b6984a424e" />
```
df.fillna(method='bfill')
```
<img width="1155" height="728" alt="image" src="https://github.com/user-attachments/assets/8b919fff-46f3-42d0-9b19-b0b6984a424e" />
```
df.fillna({'GENGER':'MALE','NAME':'SAM','ADDERESS':'POONAMALE','M1':'10','M2':20})
```
<img width="1131" height="717" alt="image" src="https://github.com/user-attachments/assets/3d421e7e-0552-4aba-8dcd-0c3f153ceb11" />
```
ir=pd.read_csv("/content/iris.csv")
print(ir)
```
<img width="785" height="353" alt="image" src="https://github.com/user-attachments/assets/5311e03f-450c-492f-8b9d-4a42dcf552a1" />
```
ir.describe()
```
<img width="777" height="388" alt="image" src="https://github.com/user-attachments/assets/ba7d96c8-b850-4af5-b844-8cf0faed18e9" />
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```

<img width="748" height="583" alt="image" src="https://github.com/user-attachments/assets/53b975f0-850e-49cb-a666-41e1a3bdb29e" />
```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
```
```
print(rid['sepal_width'])
```

<img width="471" height="148" alt="image" src="https://github.com/user-attachments/assets/e63be7a9-5cd7-499b-8b92-782a83b75b54" />

```
delid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
print(delid)
```

<img width="763" height="332" alt="image" src="https://github.com/user-attachments/assets/db19e341-15e6-4acf-be8d-bf39b9228f8a" />
```
sns.boxplot(x='sepal_width',data=delid)
```

<img width="723" height="590" alt="image" src="https://github.com/user-attachments/assets/292ebd4f-f340-4fd3-aa3b-95aaee5a5b47" />
```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir['sepal_width']))
print(z)
```

<img width="698" height="572" alt="image" src="https://github.com/user-attachments/assets/a1e93db2-d53f-4f18-8b41-f82105ec6cc7" />
```
ir1=ir[z<3]
print(ir1)
```

<img width="747" height="353" alt="image" src="https://github.com/user-attachments/assets/e5fbdddf-9f6a-4a4e-940a-b3e1b977592c" />



# Result
          <<include your Result here>>
