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
# Result
          <<include your Result here>>
