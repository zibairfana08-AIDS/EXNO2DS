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
dt=pd.read_csv("titanic_dataset.csv")
dt
```
<img width="1076" height="421" alt="image" src="https://github.com/user-attachments/assets/2718495c-75b0-46e6-aa14-05af2f46c276" />

```
dt.info()
```

<img width="324" height="336" alt="image" src="https://github.com/user-attachments/assets/eb2e2805-3ad6-41cd-aacb-8e503918d6ee" />

```
dt.shape
```

<img width="108" height="37" alt="Screenshot 2026-03-28 213058" src="https://github.com/user-attachments/assets/a49a8007-909e-49d5-8939-2ae51da54eb5" />

```
dt.reset_index(inplace=True)
display(dt.head())
```

<img width="852" height="346" alt="image" src="https://github.com/user-attachments/assets/0043e77a-3b3a-4f45-86a6-45077edb36ed" />

```
dt.nunique()
```

<img width="160" height="249" alt="image" src="https://github.com/user-attachments/assets/b127215f-a9e8-402f-9eb3-d969c042a955" />

```
dt["Survived"].value_counts()
```

<img width="208" height="80" alt="image" src="https://github.com/user-attachments/assets/71ca0b60-9e05-4b24-ad76-60fc8c96e037" />

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

<img width="232" height="80" alt="image" src="https://github.com/user-attachments/assets/681f08cd-d5bf-4c1b-978b-a29c590d3d09" />

```
sns.countplot(data=dt,x="Survived")
```

<img width="610" height="472" alt="image" src="https://github.com/user-attachments/assets/e5c23877-a1d2-4a0f-a142-dae020b889f4" />

```
dt
```

<img width="848" height="728" alt="image" src="https://github.com/user-attachments/assets/22a39895-3c1a-4562-a23e-4cad7a97146e" />

```
dt.Pclass.unique()
dt.rename(columns={'Sex':'Gender'},inplace=True)
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

<img width="766" height="522" alt="image" src="https://github.com/user-attachments/assets/9cc66dae-7cc6-4509-81c7-8567b03ff03a" />

```
sns.catplot(x='Survived',hue='Gender',data=dt,kind="count")
```

<img width="576" height="522" alt="image" src="https://github.com/user-attachments/assets/a9fa4978-b5c1-4406-8ec9-36df516792f1" />

```
dt.boxplot(column="Age",by="Survived")
```

<img width="582" height="498" alt="image" src="https://github.com/user-attachments/assets/37ecd999-6272-43a0-8171-2ae1a2389fac" />

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

<img width="594" height="458" alt="image" src="https://github.com/user-attachments/assets/a85b8a05-2579-46d9-ae0a-784905836d7f" />

```
sns.jointplot(x="Age",y="Fare",data=dt)
```

<img width="589" height="627" alt="image" src="https://github.com/user-attachments/assets/689640f8-49d6-426a-8760-8f12c6bf40f4" />

```
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```

<img width="693" height="450" alt="Screenshot 2026-03-28 214240" src="https://github.com/user-attachments/assets/0a4fb302-bf28-45f1-b1c8-9135bd05f8f3" />

```
sns.catplot(data=dt,col="Survived",x="Gender",hue='Pclass',kind="count")
```

<img width="850" height="421" alt="image" src="https://github.com/user-attachments/assets/fda021ad-d1b5-4b4d-b84a-4a68a8fb9575" />

```
corr=dt.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="637" height="517" alt="image" src="https://github.com/user-attachments/assets/3415721a-a615-48a5-99ae-ab05f1115cad" />



# RESULT
        Thus exploratory data analysis has been successfully performed on the given data set.
