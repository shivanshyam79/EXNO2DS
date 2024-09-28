## EXNO2DS
## AIM:
  To perform Exploratory Data Analysis on the given data set.
## EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

CODING AND OUTPUT
import pandas as pd import numpy as np import matplotlib.pyplot as plt import seaborn as sns
df=pd.read_csv('/content/titanic_dataset.csv') df
![311416174-81451b23-08c5-45af-a00f-7e6a0d238a73](https://github.com/user-attachments/assets/a1aaacfb-d450-40b0-9b00-53b355957f7f)
df.info()
![image](https://github.com/user-attachments/assets/f27c711c-b3bd-43f6-80bf-02bc7f96b715)
df.shape
![311416428-197c0a74-6bf8-49a5-8346-b4ec4a4fba20](https://github.com/user-attachments/assets/d5dc57a4-8f38-4632-8372-dbe28f73712a)
df.head(4)
![311416490-5b03fe5c-b620-4a0e-b02d-ebc0aede1dec](https://github.com/user-attachments/assets/35822568-36e7-4721-93a4-00592317567f)
df.describe()
![311440906-a070d1bf-2f77-4890-84b4-220fd511850b](https://github.com/user-attachments/assets/33a1681a-e989-42f5-845e-2fab39b1bf1b)
df.set_index("PassengerId",inplace=True) df.describe()
![311441009-1f744a40-6898-494c-ade2-8cb82fd20c3d](https://github.com/user-attachments/assets/d292868d-f10c-4e75-896d-a49197f83e96)
df.nunique()
![311441081-6b26e9d5-48a4-4c3b-b4be-8c2d57cb2608](https://github.com/user-attachments/assets/45c74ad6-6b72-44b2-8d1b-f69d277349b5)
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) per
![311441416-2d16121a-04c0-4456-a7ba-7b37c9829cbd](https://github.com/user-attachments/assets/db9e281b-a0ee-4c7e-8114-27bdeb1996d3)
sns.countplot(data=df,x="Survived")
![311441448-e5489847-b053-48a4-b9f9-9d8bfb38f6b8](https://github.com/user-attachments/assets/ec9c7bd1-62f3-4815-a1fb-f6831578ea14)
df
![311441491-bbce6bca-d502-4dde-a4ba-a92f3e889428](https://github.com/user-attachments/assets/f96636e5-4da2-4a01-bdfc-a11b619a0cbf)
df.Pclass.unique()
![311441953-dfabb0c4-9a84-4e56-b7a4-bba2ac6c8cdc](https://github.com/user-attachments/assets/cd22d2fa-89bb-4246-8ab1-04666f91c84f)
df.rename(columns= {'Sex':'Gender'}, inplace=True) df
![311442007-fa499c3f-47a6-4db8-b07c-cfc2f7f49303](https://github.com/user-attachments/assets/41d0a1f7-150c-417e-9c70-0db9e7ba6480)
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
![311442037-c53a66dd-095d-4afd-a2c9-cacc193bf8b9](https://github.com/user-attachments/assets/2cbc15aa-2cfd-4858-8e98-0be34b5bed59)
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
df.boxplot(column="Age",by="Survived")
![311442070-59fbffc9-3d17-4cad-ad40-1d17138b07ee](https://github.com/user-attachments/assets/6d2a00ee-91ff-40c5-b37f-eda16dc215af)
sns.scatterplot(x=df["Age"],y=df["Fare"])
![311442108-6167688c-41f9-4924-a4aa-d59d3c227ca9](https://github.com/user-attachments/assets/ea030fbb-b0d1-4e92-9a15-9e5bc17b8c40)
sns.jointplot(x="Age",y="Fare",data=df)
![311442143-e2176e26-1d2a-4261-9a07-2f65b8393326](https://github.com/user-attachments/assets/19d2d7b7-3415-4985-8bee-08e5117ee5f8)
fig,ax1 = plt.subplots(figsize=(8,5)) pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
![311442159-209808e3-b7f8-4999-a32f-df0416efa132](https://github.com/user-attachments/assets/e0cd2a04-c334-4883-bab4-113c1ff04242)
sns.catplot(data=df,col = "Survived",x = "Gender",hue="Pclass",kind = "count")
![311442212-cf4f6469-0b73-4ea3-8527-fb78adb4c085](https://github.com/user-attachments/assets/4ae2e287-5d2c-4d0c-a33f-1d33871aa3ae)
corr = df.corr() sns.heatmap(corr,annot=True)
![311442236-051d5460-4f59-428a-afd0-88b82f962071](https://github.com/user-attachments/assets/071d3ce3-b0b4-44de-93a4-20479a4dae42)
sns.pairplot(df)
![image](https://github.com/user-attachments/assets/9f2285fa-3382-4404-8ecd-f0a469365983)

RESULT
    Hence performing Exploratory Data Analysis on the given data set is successful
