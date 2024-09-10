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
df = pd.read_csv('/content/titanic_dataset.csv')
df
```
![Screenshot 2024-09-03 212845](https://github.com/user-attachments/assets/4ce792a1-8136-4399-a0eb-ad4c9c58f956)
```
df.dropna(inplace=True)
```
```
df.isna().sum()
```
![Screenshot 2024-09-03 212948](https://github.com/user-attachments/assets/eb76c493-a690-448f-a7a1-f0b7682d2615)
```
df.info()
```
![Screenshot 2024-09-03 213928](https://github.com/user-attachments/assets/8304b85f-ffab-40a4-adb2-b58c1f4f4e8a)
```
df.shape
```
![Screenshot 2024-09-03 215050](https://github.com/user-attachments/assets/31cec260-9d93-4021-9ba9-a11fca070f5c)
```
df.set_index('PassengerId', inplace=True)
df.describe()
```
![Screenshot 2024-09-03 215147](https://github.com/user-attachments/assets/35bb4428-236a-4147-8684-fde2aa24bf45)
```
df
```
![Screenshot 2024-09-03 215238](https://github.com/user-attachments/assets/8bee6ffe-935b-4bf7-b7b8-677a3d04f500)
```
df.nunique()
```
![Screenshot 2024-09-03 215324](https://github.com/user-attachments/assets/e271e476-39b5-4d2a-8539-c311dba12aa0)
```
df["Survived"].value_counts()
```
![Screenshot 2024-09-03 215400](https://github.com/user-attachments/assets/65da76d6-5fc5-4877-abfe-a8d244cbd1e5)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2024-09-03 215500](https://github.com/user-attachments/assets/6318fbe4-e0c8-4ef7-8e3a-eadb6c11aad3)
```
import seaborn as sns
sns.countplot(data=df, x="Survived")
```
![Screenshot 2024-09-03 215615](https://github.com/user-attachments/assets/f0119e08-1df4-42f6-b1d9-94812e2e4ad1)
```
df
```
![Screenshot 2024-09-03 215656](https://github.com/user-attachments/assets/27fa1cee-ca1c-4c7d-8db6-125fa2bac13c)
```
df.Pclass.unique()
```
![Screenshot 2024-09-03 215737](https://github.com/user-attachments/assets/4f9517d3-e7de-46fb-8016-0e2360155e04)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2024-09-03 215824](https://github.com/user-attachments/assets/66f847dc-7c00-4b81-ab46-fe76c9f6bf7f)
```
sns.catplot(x='Gender',col='Survived',kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-09-03 215909](https://github.com/user-attachments/assets/855144fc-2aa1-42ef-bf3d-e65e1fc5497c)
```
sns. catplot(x='Survived', hue="Gender", data=df, kind = "count" )
```
![Screenshot 2024-09-03 215958](https://github.com/user-attachments/assets/d573d9a2-5507-4f29-9bed-b2b4552550d2)
```
sns. catplot(data=df, col = "Survived", x = "Gender", hue="Pclass", kind = "count")
```
![Screenshot 2024-09-03 220042](https://github.com/user-attachments/assets/e672afa5-f1f7-446f-8ff3-099fe9807deb)
```
df_numeric = df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2024-09-03 220119](https://github.com/user-attachments/assets/1d718dbe-e339-44d9-a364-7a7e672737cb)
```
sns.pairplot(df)
```
![Screenshot 2024-09-03 220213](https://github.com/user-attachments/assets/a12fd6cb-f919-4707-96ea-a0dbdb3ad128)


# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.

