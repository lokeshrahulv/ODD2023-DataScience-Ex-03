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

## isnull.sum
<img width="188" alt="273396369-9ebd94a5-62c1-43c7-a4eb-cd923aecc27c" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/bb1001cc-2bac-4c3a-818d-d8626a7b5adc">

## info
<img width="314" alt="273396375-b5fc0f02-fc7f-4dba-b6f6-db9d25357d0a" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/b3a8a3e1-9bf9-4567-91b6-8201a72592d1">

## box plot
<img width="386" alt="273396384-0a16f906-3869-4609-ab86-32c63bd4f8dd" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/d0c2e04f-d015-453e-9686-489a27f60afa">

## count plot
<img width="414" alt="273396391-595d8f14-414e-4a90-83c6-13a2f326f5d5" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/d0a71b71-b073-436c-bbd0-1b8a5cb63ce3">

## distplot
<img width="413" alt="273396399-d67d3a7b-e871-4867-b94c-dbb3890089e7" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/203e5f92-72fd-4168-a776-4e7e891e5a5a">

## histplot
<img width="422" alt="273396404-919e58d7-b05c-43a9-87fc-babe34e5e33a" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/a73dce02-ad3b-4a5c-8711-1328c35ee323">

## SuperStore Dataset
## head
<img width="606" alt="273396409-ed2e97af-67a4-475d-8eb3-f36ecac03eb3" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/94504121-4f41-444f-bf12-4ededaf9c9aa">

## describe
<img width="247" alt="273396415-8b51db60-8877-4bd5-a73c-5361205b97df" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/8038e1f3-718f-43e6-9ba3-88e47a6862e0">

## isnull.sum
<img width="133" alt="273396418-4a4d018f-5b29-42a4-890b-cf6418826ce0" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/d5f3a039-04c8-4e92-9fee-f9794363b688">

## info
<img width="273" alt="273396421-ededc383-c677-4489-bd54-a93ab8e0b054" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/508c772c-69a6-434c-be5e-40de0de966a6">

## box plot
<img width="382" alt="273396424-a126e036-ae49-47aa-849b-aa5049fbd62e" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/14c906c0-aeaf-45ed-93bc-9a42bd74ba1b">

## count plot
<img width="427" alt="273396426-61a3dbb0-5fe7-4fb2-92bd-e1700100729e" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/21dcc13a-f265-4fd6-9fbc-795c6b64ad49">

## distplot
<img width="418" alt="273396429-365d8b0e-638d-4880-922d-42a82456097a" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/89381d8f-bb5e-4dbd-814f-de1ac7d94ddd">

## Employee_sal Dataset
## head
<img width="257" alt="273396432-db895ae7-33b1-4584-8798-ecf546c48034" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/07c920b5-690c-4eec-9df7-a0c06fad1662">

## isnull.sum
<img width="155" alt="273396437-76f0a291-d1c9-4da5-97a2-fe3212d2b0e4" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/73c33066-2caf-4b14-a927-3c9f78fbada5">

## describe
<img width="344" alt="273396443-e450d596-b769-44fd-8915-92f39af7a116" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/6cd980f1-d0c7-4ffb-a1cb-5865ea3f5bee">

## info
<img width="260" alt="273396451-81125fdb-49eb-4d9a-a9e4-1de34f3416d3" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/d9b3499c-0458-450f-98de-a09bce179b8c">

## box plot
<img width="383" alt="273396456-d3621a00-dd3f-4d8b-8b68-c0c27205f6fc" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/ebfe4c8a-2df7-41df-b84c-62b7d7eecc4b">

## count plot
<img width="392" alt="273396460-c063d9c0-7e88-4a17-b72c-d5aefc62628d" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/30a173f5-0db9-45d0-bb56-919a1ac9f2d5">

## distplot
<img width="420" alt="273396464-acc1ec10-3877-4151-84bb-83dfb8bbca3b" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/f8a17402-8a7f-468e-9427-0b59e60d8de6">

## histplot
<img width="410" alt="273396471-e23b8f17-2b67-47d5-a713-bee2f4120195" src="https://github.com/lokeshrahulv/ODD2023-DataScience-Ex-03/assets/118423842/7bb572b3-aa9c-4cc2-933d-18da5d626a51">

Result
Thus we have read the given data and performed the univariate analysis with different types of plots.
