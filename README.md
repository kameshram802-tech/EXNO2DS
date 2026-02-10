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
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
dt
```
<img width="1222" height="400" alt="Screenshot 2025-10-04 214250" src="https://github.com/user-attachments/assets/fe1344b3-cca1-43f0-b944-fc2b79e2a614" />

```py
dt.info()
```
<img width="727" height="382" alt="Screenshot 2025-10-05 112758" src="https://github.com/user-attachments/assets/de0233a4-cba0-41ea-9f3a-f64ad43d666d" />

```py
dt.shape
```
<img width="453" height="41" alt="Screenshot 2025-10-05 112922" src="https://github.com/user-attachments/assets/3f5fff59-10e7-482c-b661-396b381464d4" />

```py
dt.nunique()
```
<img width="601" height="267" alt="Screenshot 2025-10-05 113018" src="https://github.com/user-attachments/assets/41d206d8-2d1c-4fcf-9da7-06c46c2dbf42" />

```py
dt["Survived"].value_counts()
```
<img width="449" height="76" alt="Screenshot 2025-10-05 113113" src="https://github.com/user-attachments/assets/bd848d9d-d3df-4cfe-ace2-5ba4587721f8" />

```py
per=(dt["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
<img width="372" height="83" alt="Screenshot 2025-10-05 113203" src="https://github.com/user-attachments/assets/c295eb30-5901-49eb-8f0b-b4a14368e919" />

```py
sns.countplot(data=df,x="Survived")
```
<img width="750" height="536" alt="Screenshot 2025-10-05 113253" src="https://github.com/user-attachments/assets/cc91cc99-a796-49b2-a3ae-cb38d0239d61" />

```py
dt
```
<img width="1128" height="394" alt="{6408F5C2-05D0-47D3-8D4D-586E61CC0C20}" src="https://github.com/user-attachments/assets/fc508acc-d0ee-44fe-a45d-d8987b54aada" />

```py
dt.Pclass.unique()
```
<img width="359" height="39" alt="image" src="https://github.com/user-attachments/assets/b51fb927-37b2-4e7b-b3e7-f7a86ce8706d" />

```py
dt.rename(columns={'sex':'Gender'},inplace=True)
dt
```
<img width="1127" height="396" alt="{6FD5A0AA-5CE2-4E36-8564-7CA1C1F236BC}" src="https://github.com/user-attachments/assets/62c834c4-aab2-4042-a757-b42a2abf6e1b" />

```py
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
<img width="912" height="601" alt="{A4753BDA-3BD3-46B7-A6FC-39C43457C15C}" src="https://github.com/user-attachments/assets/80ba15aa-27ac-4738-baa1-81640d95a9fa" />

```py
df.boxplot(column='Age',by="Survived")
```
<img width="700" height="567" alt="{1F0250D2-F8D2-4E0C-B9FE-2E27F04FB2A6}" src="https://github.com/user-attachments/assets/1660f322-2512-4d2d-9bdc-5d4f23d95db1" />

```py
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
<img width="722" height="534" alt="{56EF6170-4AEE-4B4A-9E32-DBC94220DF20}" src="https://github.com/user-attachments/assets/2b06aea9-84db-4d0f-b780-7277af551be4" />

```py
sns.jointplot(x="Age",y="Fare",data=dt)
```
<img width="693" height="707" alt="{B347B447-CBB1-4BC8-B6C8-FCA8ACE71CD7}" src="https://github.com/user-attachments/assets/3d0f62db-a9ca-4a22-beee-ebd16e7c8a1b" />

```py
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
<img width="791" height="597" alt="{68C3EF67-6A18-4B6F-B364-93BCCF829D2C}" src="https://github.com/user-attachments/assets/33aec689-2ef8-4bfd-9ec0-6776abbbffe3" />

```py
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
<img width="863" height="517" alt="{0EC1EEB2-ACEC-4348-9AF3-5B4CA682A25C}" src="https://github.com/user-attachments/assets/228b775d-c384-40d8-b4b8-b4805e370b37" />

```py
import seaborn as sns
sns.countplot(data=df)
df
```
<img width="856" height="525" alt="image" src="https://github.com/user-attachments/assets/68a3920d-35e0-4ca5-a519-a8a4bee51b77" />

```py
sns.countplot(x="Survived",hue="Gender",data=df)
```
![WhatsApp Image 2025-10-07 at 16 12 16_e89518c6](https://github.com/user-attachments/assets/380677ea-ee44-4662-8b01-50c8ff061397)

```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="violin)
```
![WhatsApp Image 2025-10-07 at 16 14 56_91947bbc](https://github.com/user-attachments/assets/560224fd-33f5-414d-9f24-532720b83f14)

```py
sns.boxplot(data=df)
```
![WhatsApp Image 2025-10-07 at 16 17 38_c4c7bf84](https://github.com/user-attachments/assets/45f2522d-1e10-4c2f-8ffe-fb927ead37df)

```py
df.boxplot(column="Survived",by="Gender")
```
![WhatsApp Image 2025-10-07 at 16 19 05_133943b2](https://github.com/user-attachments/assets/a76a3ae5-6733-4f19-bdce-b9f7aaead259)

```py
sns.scatterplot(data=df)
```
<img width="707" height="522" alt="{5A781AB3-B1BC-45DE-B3C8-BDC9A7010140}" src="https://github.com/user-attachments/assets/df15f556-b5e5-4820-ab91-85c223fc3e39" />

```py
sns.joinplot(x='Age',y='Fare',data=df,kind="kide")
```
<img width="805" height="810" alt="{8BD91B47-AD55-4D35-8E00-32ABBB042544}" src="https://github.com/user-attachments/assets/91289104-9a1a-4feb-9436-31e6320056ee" />

```py
sns.joinplot(x='Age',y='Fare',data=df,kind="hist")
```
<img width="745" height="674" alt="{A7D3A380-A726-434C-A4DB-35FDD083D12E}" src="https://github.com/user-attachments/assets/feec1613-75cf-45eb-b88b-a887c59c56e6" />

```py
sns.pairplot(data=df)
```
<img width="835" height="854" alt="{BBEBB40C-54A8-43FC-830E-DC600A754865}" src="https://github.com/user-attachments/assets/2855fb70-3d33-4341-93f4-0bf441386682" />

```py
corr =dt.corr()
sns.heatmap(corr,annot=True)
```
<img width="583" height="421" alt="{5E0B6598-EC2B-4865-B6EF-BDF30BEAF667}" src="https://github.com/user-attachments/assets/f7415d55-59b4-4103-a492-fc88ee106cdd" />

```py
sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')
```
<img width="704" height="352" alt="image" src="https://github.com/user-attachments/assets/cd010233-da96-464d-a416-6c73894520f1" />

## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
