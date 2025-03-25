EXNO2DS-Exploratory Data Analysis
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
Developed by: S.Rithik Ram

Register no: 212224230229
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
rr=pd.read_csv("/content/titanic_dataset.csv")
rr
```
![Screenshot 2025-03-25 105415](https://github.com/user-attachments/assets/261053f4-8950-4699-892e-394f11d9f942)

```
rr.info()
```

![Screenshot 2025-03-25 110827](https://github.com/user-attachments/assets/1d14e222-e0cc-4d4f-85b9-154fdfd6dd1c)

```
rr.shape
```

![Screenshot 2025-03-25 111106](https://github.com/user-attachments/assets/4b862eec-174a-438e-9462-09d540776561)

```
 rr.set_index("PassengerId",inplace=True)
 rr.describe()
```

![Screenshot 2025-03-25 111118](https://github.com/user-attachments/assets/2fb6b147-9095-4db2-8704-6a450edaa157)

```
rr.shape
```

![Screenshot 2025-03-25 111313](https://github.com/user-attachments/assets/bde8c335-691c-4a48-9bf8-35314c0b1c81)

```
rr.nunique()
```

![Screenshot 2025-03-25 111321](https://github.com/user-attachments/assets/d0314071-12a0-4bde-a2f0-f261a51df453)

```
rr["Survived"].value_counts()
```

![Screenshot 2025-03-25 111441](https://github.com/user-attachments/assets/72c7fa90-deed-483e-9b2e-15b94784fcf6)




```
per=(rr["Survived"].value_counts()/rr.shape[0]*100).round(2)
per
```

![Screenshot 2025-03-25 111452](https://github.com/user-attachments/assets/0107c8b7-d9f1-4dbe-8c78-2960f50d0d7b)

```
sns.countplot(data=rr,x="Survived")
```

![Screenshot 2025-03-25 111829](https://github.com/user-attachments/assets/f21f7879-5ed7-4119-87db-3d50c47df034)

```
rr
```

![Screenshot 2025-03-25 111914](https://github.com/user-attachments/assets/a44530c9-4ae9-4849-a0cb-45a9f32bcf89)


```
rr.Pclass.unique()
```

![Screenshot 2025-03-25 112028](https://github.com/user-attachments/assets/1d6b9a1f-6945-4610-bcc1-b6d43cd81594)

```
 rr.rename(columns={'Sex':'Gender'},inplace=True)
 rr
```

![Screenshot 2025-03-25 112047](https://github.com/user-attachments/assets/423c9c2f-3273-49ba-bc84-07c6996d0026)


 Bivariate Analysis:

 ```
sns.catplot(x="Gender",col="Survived",kind="count",data=rr,height=5,aspect=.7)
```

![Screenshot 2025-03-25 112511](https://github.com/user-attachments/assets/2da8b52c-6787-4748-bcf6-f8d442e81b68)

```
sns.catplot(x="Survived",hue="Gender",data=rr,kind="count")
```

![Screenshot 2025-03-25 112632](https://github.com/user-attachments/assets/63b0b78e-a571-454f-ad43-6a079f83fa87)

```
rr.boxplot(column="Age",by="Survived")
```

![Screenshot 2025-03-25 112640](https://github.com/user-attachments/assets/1791bc7c-f8a6-4a81-8298-1f8ad05a97d8)


```
sns.scatterplot(x=rr["Age"],y=rr["Fare"])
```

![Screenshot 2025-03-25 112918](https://github.com/user-attachments/assets/df9490e4-90c9-49f2-9a02-baaf3170aaf1)

```
sns.jointplot(x="Age",y="Fare",data=rr)
```

![Screenshot 2025-03-25 112927](https://github.com/user-attachments/assets/7d01edbf-127b-427e-9d63-fc9e7c44850a)


```
 fig, ax1 = plt.subplots(figsize=(8,5))
 plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=rr)
```


![Screenshot 2025-03-25 113142](https://github.com/user-attachments/assets/f61f1ddc-7423-41e2-8d20-262be9f123d0)

```
sns.catplot(data=rr,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![Screenshot 2025-03-25 113159](https://github.com/user-attachments/assets/82d306df-746a-46e0-9a99-236935fb5eb9)


```
numerical_cols = rr.select_dtypes(include=np.number).columns
corr = rr[numerical_cols].corr()
sns.heatmap(corr, annot=True)
```

![Screenshot 2025-03-25 113330](https://github.com/user-attachments/assets/06f7f844-ff65-4691-8fbd-639c0421856e)

```
sns.pairplot(rr)
```


![Screenshot 2025-03-25 113441](https://github.com/user-attachments/assets/6a03e38f-3003-4abb-a819-078ca89c5829)










# RESULT
       We have performed Exploratory Data Analysis on the given data set successfully.
