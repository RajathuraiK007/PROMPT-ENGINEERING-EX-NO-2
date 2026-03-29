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
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("C:\\Users\\G.POORNIMA DEVI\\Downloads\\titanic_dataset (1).csv")
df
```

<img width="1520" height="689" alt="image" src="https://github.com/user-attachments/assets/2aff3a50-3c64-4d3c-a1cb-391f09f8f8f8" />

```
df['Age']=df['Age'].fillna(df['Age'].median())
df
```
<img width="1533" height="708" alt="image" src="https://github.com/user-attachments/assets/d4b3d3a9-49a1-4642-bc78-1e122ed5eba0" />

```
plt.title("Outlier Detection Using Box Plot")
sns.boxplot(x=df['Age'])
```

<img width="1290" height="756" alt="image" src="https://github.com/user-attachments/assets/c8dd8687-514d-413b-b9fd-2d78b8a9fca7" />

```
#IQR
Q1=df['Fare'].quantile(.25)
Q3=df['Fare'].quantile(.75)
IQR=Q3-Q1
upper=Q3+1.5*IQR
lower=Q1-1.5*IQR
df=df[(df['Fare']>=lower) & (df['Fare']<=upper)]
df
```

<img width="1542" height="778" alt="image" src="https://github.com/user-attachments/assets/378616a1-75e7-498d-b4b5-56c841006e8d" />

```
#countplot
plt.title('Gender Count')
sns.countplot(x='Sex',data=df)
```

<img width="1462" height="715" alt="image" src="https://github.com/user-attachments/assets/c17e2a52-ef19-43a7-b30d-62455aeb231b" />

```
sns.displot(x="Age",data=df,kind="kde")
```

<img width="1352" height="725" alt="image" src="https://github.com/user-attachments/assets/6ad9f2db-700a-4ea5-8784-a8a820863591" />

```
sns.displot(x="Age",data=df,hue="Sex",kind="kde")
```

<img width="1341" height="744" alt="image" src="https://github.com/user-attachments/assets/7775d228-37f5-493a-b951-6afba2567b9e" />

```
sns.displot(x="Age",data=df,hue="Sex",kind="hist")
```

<img width="1339" height="729" alt="image" src="https://github.com/user-attachments/assets/eaf67230-ec7f-43c0-a64e-f162753a0472" />

```
sns.displot(x="Age",data=df,hue="Sex",kind="ecdf")
```

<img width="1350" height="747" alt="image" src="https://github.com/user-attachments/assets/aa90d475-ecc4-405b-9e0b-59bef5ded999" />

```
cross_tab=pd.crosstab(df["Sex"],df["Fare"])
print(cross_tab)
```

<img width="1344" height="360" alt="image" src="https://github.com/user-attachments/assets/ad865f44-3e40-4df2-ab64-153c8f82bba3" />

```
cross_tab=pd.crosstab(df["Sex"],df["Age"])
print(cross_tab
```

<img width="1348" height="377" alt="image" src="https://github.com/user-attachments/assets/acde216a-c74b-4af0-a461-593b7e5d8ac3" />

```
sns.heatmap(cross_tab,cmap="Blues",annot=True,fmt="d")
```

<img width="1265" height="572" alt="image" src="https://github.com/user-attachments/assets/8af64fb2-ae99-46a3-bba3-0f1e28a986df" />

```
sns.heatmap(cross_tab,cmap="YlGnBu",annot=True,fmt="d")
```

<img width="1275" height="582" alt="image" src="https://github.com/user-attachments/assets/9531842d-f103-4b69-95ab-b867e1f4f686" />


# RESULT
The Program and The Output has been sucessfully Verified along with the Visualization 
