# Ex-09 Data Visualization 2

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
NAME : SANJAY
REG NO : 212222230132
```
```
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
df.head()
df.isnull().sum()
#ANALYZING OUTLIERS
plt.title("Data with Outliners")
sns.boxplot(data=df)
plt.show()
#REMOVINF OUTLIERS
cols=["size","tip","total_bill"]
q1=df[cols].quantile(0.25)
q3=df[cols].quantile(0.75)
iqr=q3-q1
df=df[~((df[cols]<(q1-1.5*iqr))|
(df[cols]>(q3+1.5*iqr))).any(axis=1)]
plt.title("Outliers Removed")
sns.boxplot(data=df)
plt.show()
sns.barplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="center")
plt.title("highest total bill amount by day of the week")
plt.figure(figsize=(6,3))
sns.boxplot(x=df["smoker"],y=df["tip"],hue=df["smoker"])
plt.title("Tip amount given by Smokers and Non-Smokers")
df["tip_percent"]=df["tip"]/df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
sns.barplot(x=df["sex"],y=df["tip"],hue=df["sex"])    
plt.legend(loc="best")
plt.title("Highest Tips Based on Gender")
sns.scatterplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="best")
plt.title("Relation Between Total Bill Amount by Dayof the Week")
sns.histplot(data=df,x="total_bill",hue="time",lement="step",stat="density")
plt.title("Total Bill Amounts by Time of Day")
plt.show()
plt.figure(figsize=(6,3))
sns.barplot(x=df["size"],y=df["total_bill"],hue=df["size"])
plt.title("Highrst Average Total Bill Amount by DiningParty Size")
sns.boxplot(x="day", y="tip", data=df)
plt.title("Distribution of Tip Amount by Day\of Week")
plt.show()
plt.figure(figsize=(6,3))
sns.violinplot(x="time",y="tip",data=df)
plt.title("Tip Amount Based on Type of Service")
sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between Total Bill Amount and Tip Amount")
plt.show()
```

# OUPUT
![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/ac9dde92-7eb6-453e-b65c-de997c0fa745)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/066ae1af-4f7e-47e1-83ab-a2d7351a28ed)
![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/81264bb1-9991-4a6c-a377-585f73934dd4)

<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/398748c7-b70d-407f-96d7-272e554e417c)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/9143645b-627a-4ea0-a58d-7b988a369719)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/bfdb5320-1aa9-461e-81e0-e131724fa230)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/45d79435-db9a-4c21-a10e-b870bf3d99ee)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/90bf0647-035f-4aab-b941-30f8416b9aa1)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/dab44b36-06c3-4a5d-8977-ace6c39b022a)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/eaf17dec-7032-43e0-8bfb-6c8779296cb9)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/25039810-03ff-4912-9fec-e4e868607213)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/9086d34d-3608-473f-9c14-09e7058f243b)
<br>

![image](https://github.com/22002102/ODD2023-Datascience-Ex-09/assets/119091638/06d5bbc6-8831-4bea-a965-2f95aafc7dc5)


### RESULT:
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.
