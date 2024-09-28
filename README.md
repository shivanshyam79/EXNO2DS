EXNO2DS
AIM:
  To perform Exploratory Data Analysis on the given data set.
EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

CODING AND OUTPUT:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
![363832796-4991394c-5d9e-499e-ad37-aa83b269379f](https://github.com/user-attachments/assets/9b0b5c3f-034d-4d0e-a831-0283ed5a8346)


df.info()
![363832917-2c69e058-85b5-4146-bb61-570a48649115](https://github.com/user-attachments/assets/5f34ef1c-cb8b-4948-b474-b93da0e9f940)


df.shape
![363833030-aeaa657f-1d20-4b44-9ccc-167817f98859](https://github.com/user-attachments/assets/c5b5cb41-062c-4d4a-9924-d4334902823f)


df.nunique()
![363833219-32d6170d-da8d-4239-adee-8b31a3587705](https://github.com/user-attachments/assets/54115b4b-5fc6-437c-af33-ddc7549624d5)


df["Survived"].value_counts()
![363833314-7e89bb1e-60ae-44d3-a52b-85e17de32d8f](https://github.com/user-attachments/assets/eaa7c879-aab5-4318-8499-9ee6ef0c9670)


per=(df["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
![363833476-da947b19-65a5-477c-9b32-fbf79257e187](https://github.com/user-attachments/assets/e63f21a8-239f-4450-bf63-9b2700d39441)


df.describe()
![363833565-7f0baafe-9faa-4971-a9f5-97ebdd06a33e](https://github.com/user-attachments/assets/831c321c-1469-49c8-8ef0-3aed1cf50bac)


sns.countplot(data=df,x="Survived")
![363833666-1f03c123-1189-4979-b51e-eb2b1f671a19](https://github.com/user-attachments/assets/c7da34c9-980f-4dfb-85a5-fae6d213676d)


df.Pclass.unique()
![363833817-21531458-eca3-4981-a4ee-411428ca8bae](https://github.com/user-attachments/assets/8e4a5df7-5028-441c-8061-28d52df0d4a3)


df.rename(columns = {'sex': 'Gender'},inplace = True)
df
![363834025-3a15901a-0560-4954-8cbe-42571b01c1ef](https://github.com/user-attachments/assets/fdbfceb8-0ca3-4508-811b-2c702ac687b3)


sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
![363835593-9a5264af-3d8d-49a3-b86d-10f5d640dc9f](https://github.com/user-attachments/assets/a0023465-18da-4c73-9416-a9fcbdc9c376)


sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
![363835768-0d2943d4-18de-4fd7-ad42-fa93d85321a1](https://github.com/user-attachments/assets/fb8d7f52-a7ea-44fc-8f00-34ea73fb7d0e)


df.boxplot(column="Age",by="Survived")
![363835958-88864778-988a-4a7b-9b7b-e4d7b29dc60e](https://github.com/user-attachments/assets/0221b170-c7a5-4cfa-af83-b01b6af36bc5)


sns.scatterplot(x=df["Age"],y=df["Fare"])
![363836125-901bfcc3-b35f-483d-ba60-4a197d691a1f](https://github.com/user-attachments/assets/c3bb5d75-44d2-426c-a846-def1af804b69)


sns.jointplot(x="Age",y="Fare",data=df)
![363836306-4a6cc90f-a12f-41b2-9551-08f3f944574b](https://github.com/user-attachments/assets/6ecd02a9-d7ab-48cc-adcd-af0638122208)


fig,ax1 = plt.subplots(figsize=(8,5))
pt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
![363836483-9097d508-96c2-4e76-94f0-5f14285b8610](https://github.com/user-attachments/assets/4bf8f530-2a2e-4188-b471-b1dede973c27)


sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
![363836684-604554dc-9112-4545-b212-abf01aef7ddf](https://github.com/user-attachments/assets/3b3e100a-9bb8-48a3-a216-84fd02bd6910)


numeric_dt = df.select_dtypes(include=['number'])
corr = numeric_dt.corr()
sns.heatmap(corr,annot=True)
![363836684-604554dc-9112-4545-b212-abf01aef7ddf](https://github.com/user-attachments/assets/11a404cd-775b-4a1b-954d-905b3018d42c)


import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
sns.pairplot(df)
![image](https://github.com/user-attachments/assets/618cca6c-e2c0-44f8-8882-3e6d0e94d267)


RESULT:
Thus the data analysis has been implemented succesfully.

