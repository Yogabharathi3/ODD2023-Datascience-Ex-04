# ODD2023-Datascience

# Ex-04-Multivariate-Analysis
# AIM :
To perform Multivariate EDA on the given data set.

# EXPLANATION :
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM :
# STEP 1 :
Import the built libraries required to perform EDA and outlier removal.

# STEP 2 :
Read the given csv file.

# STEP 3 :
Convert the file into a dataframe and get information of the data.

# STEP 4 :
Return the objects containing counts of unique values using (value_counts()).

# STEP 5 :
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6 :
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7 :
Find the pairwise correlation of all columns in the dataframe.corr() .

# STEP 8 :
Save the final data set into the file.

# Program :
```
Developed by:Yogabharathi S
Register no:212222230179
```
```
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
# OUTPUT :
# DATASET :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/3df1b52a-f769-4bc4-9339-7414cf14ca33)


# HEAD() :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/a30ea002-845c-44c9-96c5-2f25e3af6e7d)


# INFO() :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/6d0552eb-f704-47c5-b2de-365fb0ad697e)


# DESCRIBE() :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/729fdf77-3069-4c09-b235-00eb56cd8270)


# DATATYPE() :

![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/92950b3a-4ba5-41a1-91b1-a2555f578046)

# ISNULL() :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/81f662ef-3baf-49af-b7d2-0fc0249f9be1)


# Postal code has outliers :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/a3d5b9ba-be66-486a-9731-11f26c956324)


# After removing outliers from Postal Code :
# MULTIVARIATE ANALYSIS :
# SCATTER PLOT :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/bcac0060-dd8e-4b45-8623-654c64549859)
# BARPLOT :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/7a31e239-0f72-40fd-9f0e-7e288c42c68c)
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/a8d936b7-2139-4f63-a0b2-78e300cc2cd0)
# SEGMENTATION :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/38e5e199-3bfb-4ed9-80e8-f181f6e3e3d0)
# CORRESSION :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/4f9b96a8-42cb-4b07-a059-cca7a81a9be8)
# HEATMAP() :
![image](https://github.com/Yogabharathi3/ODD2023-Datascience-Ex-04/assets/118899387/6c391471-e813-405e-b707-d922d55857fd)

# RESULT :
Hence The Performance of the Multivariate EDA on the given data set is verified.
