# ODD2023-DataScience-Ex-03
# Aim:
To read the given data and perform the univariate analysis with different types of plots.

# Explanation:
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

## Algorithm:
STEP 1: Read the given data.
   
STEP 2: Get the information about the data.
   
STEP 3: Remove the null values from the data.
   
STEP 4: Mention the datatypes from the data.
   
STEP 5: Count the values from the data.
   
STEP 6: Do plots like boxplots,countplot,distribution plot,histogram plot.
   
# Program:
 ```
Developed by : Gowrisankar.p
Register number : 212222230041
 ```
  Diabetes.csv
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
```
 Output(Diabetes.csv)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/4e624a90-c3f2-4d33-a093-5e2bff1d6621)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/2749a026-4c4e-4003-b515-1782978a2760)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/7dddcebd-d7ab-4f64-b11a-fddf2705458a)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/73ad8c63-2f4b-4c99-895a-dfb1737e93fd)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/ae4eac8b-1871-47fd-bebf-42a684bbc02b)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/d0f476e5-4f08-4102-ad8b-71a2640560f5)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/93cd57ef-f3b9-4bf2-a4fe-e6df2656c9fd)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/2548c30f-aa3d-4d4a-a98c-261e01694813)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/5f583720-a43a-4001-84e3-813e6005c6c6)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/f022790e-14e4-41aa-a229-4a488cbb4ed6)
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/7a839f9f-5367-4dcf-afed-2a1ac4743a18)
 Superstore.csv
 ```
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df1=pd.read_csv('SuperStore.csv')
df1.head()
df1.describe()
df1.isnull().sum()
df1.info()
df1['Postal Code']=df1['Postal Code'].fillna(method='ffill')
sns.boxplot(x='Postal Code', data=df1)
sns.countplot(x='Postal Code',data=df1)
sns.distplot(df1["Postal Code"])
sns.histplot(x="Postal Code",data=df1)
```
  Output(SuperStores.csv)
  https://user-images.githubusercontent.com/118707073/272160258-c01fd877-a11f-4f76-942e-f8b61469d0bd.png
  https://user-images.githubusercontent.com/118707073/272160328-e03e85ee-9873-4f11-9182-6435206a0570.png
  https://user-images.githubusercontent.com/118707073/272160278-027f846a-c889-4446-b217-5c9e041be521.png
  https://user-images.githubusercontent.com/118707073/272160338-d6554d40-d4ce-4ee9-8679-21e2fbf49ebf.png
  https://user-images.githubusercontent.com/118707073/272160341-50394024-0d2b-4141-95bb-0792351caf8d.png
  https://user-images.githubusercontent.com/118707073/272160355-4dc2f8ef-9d9e-4408-a4f5-28f2c7091bf0.png
  https://user-images.githubusercontent.com/118707073/272160370-8c10f57f-7bea-4eb2-8b3d-cb91624fb331.png
  https://user-images.githubusercontent.com/118707073/272160440-242cf82d-98d0-44c8-a02b-b2b7cd24650f.png
