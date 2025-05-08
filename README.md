# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/2c028e8b-fad5-48f9-92a6-b2823204e7be)

```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/eb73e825-48aa-4577-9a48-8deda2c753c8)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/38c553b8-e6b6-49d1-8f20-7c8ed0930383)
```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/f9142c3c-3cdc-4a3f-9a1a-1e1588989488)
```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/585239fe-96f0-425e-84e6-b3f61c69cde9)
```
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/1486a393-f406-4fe5-a798-fc33c0223b12)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/398a189a-debc-498a-b717-34017cdbc4a0)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/f36eeaea-ca35-4150-866c-7749a12e67ed)

```
ti=pd.read_csv("/content/titanic_dataset (2).csv")
ti
```
![image](https://github.com/user-attachments/assets/48d26dae-570c-438a-928f-0201227a0c7a)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=ti, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/a19553b0-6ffc-454b-bf65-ff8990666253)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=ti, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/956433ed-0003-4025-a18f-8421421f598e)
```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/59120c1d-a631-48f1-bd37-f9426b7e0061)
```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/5f95a2ec-99e7-4669-9637-37a8d15148a0)
```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/b153d134-e406-450b-845f-d56592afdd77)
```
df=pd.read_csv("/content/titanic_dataset (2).csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/27d799b8-ea25-41b1-9209-14d8328e4e97)
```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/35b72fcb-08a3-4691-81b1-869421d5b65c)
```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/08b92502-2ad3-40d2-81d4-b043120edff9)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/fc9bc6c1-9af5-494a-802a-a0ce5cd98dd6)
```
mart=pd.read_csv("/content/titanic_dataset (2).csv")
mart
```
![image](https://github.com/user-attachments/assets/c19acf7b-3120-4b19-bac9-61a715e39d96)
```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
```
![image](https://github.com/user-attachments/assets/28c3783d-6fe5-418b-8229-34b102ca2127)
```
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/06beb721-2236-486d-8fa6-57434e448f86)
```
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/07c0b9b2-10aa-48b3-92ca-75a5135a6267)
```
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/3a261c1c-0328-4231-8506-8e260566ba77)
```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/3c571a53-9edc-43fa-86d5-a45431ea95e0)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/954dbe6f-271d-45bb-a264-e6ba8e565d94)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/6e47aca3-ef61-4cda-a4c1-1e55de5f69c1)
```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/a95330ee-dde8-485b-9e6a-9d9d07c3cc9e)

# Result:
 Thus, all the data visualization techniques of seaborn has been implemented successfully.
