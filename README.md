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
 ![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/db20dc79-e10f-4889-a204-32d3d5fc437d)
 
![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/2549724a-73ab-433b-831f-49f4f8307423)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/29c43166-9dc7-4e2c-ad2c-2ab0890c61d8)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/e1ecf630-fc64-4181-a5c4-e34842d7cd8e)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/bfe55edf-1f70-44d4-8263-25f037a53d49)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/b812f0ac-c445-4726-9472-2fe62a5a3876)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/2875bbb5-5126-4828-b669-fd26fe2b2761)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/379cc7f7-0dea-44d3-b534-92d956d85bf7)
  employeesal.csv
```
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
Output(employeesal.csv)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/60155f1c-d0d0-4519-8bba-8082d7dda279)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/1c354f16-2677-4be9-8c5a-0b44f97dca88)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/c4fa330f-716c-4e11-a5d0-c2d9a62122b4)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/82355ef3-9945-4cf2-bfd2-60d782cca75b)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/cdeda3d5-9b07-4123-b8bc-79ad66626753)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/78b52658-2159-45b9-aeb5-f18394404eb8)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/78cc6a4b-bd0d-4aa7-b720-e7d35c5b5601)

![image](https://github.com/gowrisankarponnusamy/ODD2023-DataScience-Ex-03/assets/119393123/24bcca7b-59b1-49aa-b6da-6586f6b2fa88)
# Result:
Thus we have read the given data and performed the univariate analysis with different types of plots.
  
