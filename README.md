# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df>>
```
![363832796-4991394c-5d9e-499e-ad37-aa83b269379f](https://github.com/user-attachments/assets/c68f2f03-4302-4ca5-ab7e-d1cda0f41033)
df.info()
![363832917-2c69e058-85b5-4146-bb61-570a48649115](https://github.com/user-attachments/assets/4eac38a5-2423-4c9f-b343-1ee95bf10d97)
df.shape
![363833030-aeaa657f-1d20-4b44-9ccc-167817f98859](https://github.com/user-attachments/assets/a9359df7-7427-44e1-9804-b03848146c6f)
df.nunique()
![363833219-32d6170d-da8d-4239-adee-8b31a3587705](https://github.com/user-attachments/assets/ad46f420-c8ef-48dd-8eb2-a18794da4518)
df["Survived"].value_counts()
![363833314-7e89bb1e-60ae-44d3-a52b-85e17de32d8f](https://github.com/user-attachments/assets/0589369c-9707-413f-9049-3ec2a1de32fb)
per=(df["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
![363833476-da947b19-65a5-477c-9b32-fbf79257e187](https://github.com/user-attachments/assets/2a804dbe-e07e-43fc-bf0c-9909ca8e7dbd)
df.describe()
![363833565-7f0baafe-9faa-4971-a9f5-97ebdd06a33e](https://github.com/user-attachments/assets/db6608ce-59ae-4925-ba2b-1426ee551d4b)
sns.countplot(data=df,x="Survived")
![363833666-1f03c123-1189-4979-b51e-eb2b1f671a19](https://github.com/user-attachments/assets/6aa88433-5c01-4654-b5cb-6da1c33a1559)
df.Pclass.unique()
![363833817-21531458-eca3-4981-a4ee-411428ca8bae](https://github.com/user-attachments/assets/85912ab2-2a91-40d1-99be-91b4611dc377)
df.rename(columns = {'sex': 'Gender'},inplace = True)
df
![363834025-3a15901a-0560-4954-8cbe-42571b01c1ef](https://github.com/user-attachments/assets/627ff9a2-f64d-447d-971d-063636e0fb13)
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
![363835593-9a5264af-3d8d-49a3-b86d-10f5d640dc9f](https://github.com/user-attachments/assets/bdfbf494-603b-4d16-84f6-b08e328e8323)
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
![363835768-0d2943d4-18de-4fd7-ad42-fa93d85321a1](https://github.com/user-attachments/assets/2d8b097f-29ce-4d9f-81e3-89258069607b)
df.boxplot(column="Age",by="Survived")
![363835958-88864778-988a-4a7b-9b7b-e4d7b29dc60e](https://github.com/user-attachments/assets/b0805cc8-acb7-4d4a-9410-acbd2149aa68)
sns.scatterplot(x=df["Age"],y=df["Fare"])
![363836125-901bfcc3-b35f-483d-ba60-4a197d691a1f](https://github.com/user-attachments/assets/ea61933d-739b-4087-9b39-15b8d7c5135a)
sns.jointplot(x="Age",y="Fare",data=df)
![363836306-4a6cc90f-a12f-41b2-9551-08f3f944574b](https://github.com/user-attachments/assets/6141dac2-6051-4449-b87d-da927ccb7ea1)
fig,ax1 = plt.subplots(figsize=(8,5))
pt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
![363836483-9097d508-96c2-4e76-94f0-5f14285b8610](https://github.com/user-attachments/assets/e25623d8-5fb4-4e62-9dca-bdf7aa788063)
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
![363836684-604554dc-9112-4545-b212-abf01aef7ddf](https://github.com/user-attachments/assets/568086d3-cc23-4bcb-a091-d9aad47214fe)
numeric_dt = df.select_dtypes(include=['number'])
corr = numeric_dt.corr()
sns.heatmap(corr,annot=True)
![363843794-1f1ce434-73b7-451c-ae81-465bbac1d935](https://github.com/user-attachments/assets/1f7dc213-9396-4d9f-b811-384df72776d9)
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
sns.pairplot(df)
![Uploading 363837192-4dd5dee9-f124-4b48-a70a-b3ff7a06cfb5.png…]()

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
