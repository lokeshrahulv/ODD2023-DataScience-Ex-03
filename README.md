# Ex:03 Univariate Analysis
## Aim
To read the given data and perform the univariate analysis with different types of plots.

## Explanation
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

## Algorithm
Step 1: Read the given data.
Step 2: Get the information about the data.
Step 3: Remove the null values from the data.
Step 4: Mention the datatypes from the data.
Step 5: Count the values from the data.
Step 6: Do plots like boxplots,countplot,distribution plot,histogram plot.

## Code
```
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('diabetes.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
sns.boxplot(x="Glucose",data=df)
Glucose_q1 = df['Glucose'].quantile(0.25)
Glucose_q3 = df['Glucose'].quantile(0.75)
Glucose_IQR = Glucose_q3 - Glucose_q1
Glucose_low = Glucose_q1 - 1.5 * Glucose_IQR
Glucose_high = Glucose_q3 + 1.5 * Glucose_IQR
df=df[((df['Glucose']>=Glucose_low)&(df['Glucose']<=Glucose_high))]
sns.countplot(x="Glucose",data=df)
sns.distplot(df['Glucose'])
sns.histplot(x="Glucose",data=df)

import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('SuperStore.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
df['Postal Code']=df['Postal Code'].fillna(method='ffill')
sns.boxplot(x='Postal Code', data=df)
sns.countplot(x='Postal Code',data=df)
sns.distplot(df["Postal Code"])
sns.histplot(x="Postal Code",data=df)

import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('employeesal.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
sns.boxplot(x='Experience_Years',data=df)
sns.countplot(x="Experience_Years",data=df)
sns.distplot(df['Experience_Years'])
sns.histplot(x="Experience_Years",data=df)
```
## Output
## Diabetes Dataset
## head
<img width="533" alt="273396355-31334f3f-bd76-475e-8cdc-a42a32083ced" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/620d8acb-69d3-47a1-9bfd-46a4f49cc3a7">
## describe
<img width="576" alt="273396362-4bb1c854-1407-4105-b167-2295c1a7a09c" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/f01d10eb-8e6c-480a-9937-0ce9bc7d1aa9">
## 
