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
![Screenshot 2025-03-07 160821](https://github.com/user-attachments/assets/46a02c8a-73ce-465d-9fca-9d3735c6b12e)
```
df.isnull().sum()
```
![Screenshot 2025-03-07 161046](https://github.com/user-attachments/assets/5c9395e5-9981-4413-bc18-f6ac0a6846dc)
```
df.isnull().any()
```
![Screenshot 2025-03-07 161200](https://github.com/user-attachments/assets/7e91ea45-2efa-4d0f-a29d-b4806f2f91ee)
```
df.dropna()
```
![Screenshot 2025-03-07 161331](https://github.com/user-attachments/assets/6403ba30-885d-4c07-a8be-e426a7be5833)
```
df.fillna(0)
```
![Screenshot 2025-03-07 161509](https://github.com/user-attachments/assets/9cc299cd-d1df-40c8-a395-46654cc52196)
```
df.fillna(method = 'ffill')
```
![Screenshot 2025-03-07 161652](https://github.com/user-attachments/assets/5cc055b7-5e6a-4d0c-9201-e45faf1587f2)
```
df.fillna(method = 'bfill')
```
![Screenshot 2025-03-07 161843](https://github.com/user-attachments/assets/59fb0212-c661-497d-9e84-8ea34c54e365)
```
df_dropped = df.dropna()
df_dropped
```
![Screenshot 2025-03-07 162039](https://github.com/user-attachments/assets/66fd3189-11b5-49d2-b6f8-147771f26260)

```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![Screenshot 2025-03-07 162153](https://github.com/user-attachments/assets/abc518c7-84b7-4e6f-99d4-1d1910cf6057)


              IQR(Inter Quartile Range
```
import pandas as pd
ir=pd.read_csv('iris.csv')
ir
```
![Screenshot 2025-03-07 162640](https://github.com/user-attachments/assets/92584654-db08-44bd-96cb-baf9f38d1ee0)
```
ir.describe()
```
![Screenshot 2025-03-07 162801](https://github.com/user-attachments/assets/29f8482a-1590-428a-861c-939af65281eb)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![Screenshot 2025-03-07 164643](https://github.com/user-attachments/assets/20b485cc-e23d-49e0-b366-27b8f989b4ab)
![Screenshot 2025-03-07 165101](https://github.com/user-attachments/assets/fccaf693-98f0-44b4-9b2e-38cf29904d3f)

```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![Screenshot 2025-03-07 165303](https://github.com/user-attachments/assets/8dda5b2c-08b8-4696-888d-4ce6c1893a8a)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=delid)
```
![Screenshot 2025-03-07 173844](https://github.com/user-attachments/assets/7618fbd2-4de8-43cc-8584-4ddbd0a3f2dd)

      Z-Score
```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("heights.csv")
dataset
```
![Screenshot 2025-03-07 174106](https://github.com/user-attachments/assets/34982d09-0403-4338-ad08-cf3b9856c435)
![Screenshot 2025-03-07 174422](https://github.com/user-attachments/assets/3cdc0561-a197-48a7-97eb-c74bd3fe31fc)
```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![Screenshot 2025-03-07 174628](https://github.com/user-attachments/assets/e2d47e51-2fe7-4383-a5db-50986652640e)
```
z = np.abs(stats.zscore(df['height']))
z
```
![Screenshot 2025-03-07 174831](https://github.com/user-attachments/assets/dbd0b5f9-18d0-4b23-b616-f8fa3d8cc92c)
```
df1 = df[z<3]
df1
```
![Screenshot 2025-03-07 175004](https://github.com/user-attachments/assets/4a21a093-0b07-402b-a3d8-da88b825508c)



















         
# Result
      Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method   
