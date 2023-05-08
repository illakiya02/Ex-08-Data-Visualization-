# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

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
#Reading the given dataset
import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')
df.head()
#Data Visualization using Seaborn
import seaborn as sns
from matplotlib import pyplot as plt
#1.Line Plot
plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')
#2.Scatterplot
sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
#3.Boxplot
sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)
#4.Violin Plot
sns.violinplot(x="Profit",data=df)
#5.Barplot
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
#6.Pointplot
sns.pointplot(x=df["Quantity"],y=df["Discount"])
#7.Count plot
sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)
#8.Histogram
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
#9.KDE Plot
sns.kdeplot(x="Profit", data = df,hue='Category')
#Data Visualization Using MatPlotlib
#1.Plot
plt.plot(df['Category'], df['Sales'])
plt.show()
#2.Heatmap
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
#3.Piechart
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()
df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()
#4.Histogram
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
#5.Bargraph
plt.bar(df.index,df['Category'])
plt.show()
#6.Scatterplot

# OUPUT
Reading the given dataset
## Data Visualization Using Seaborn: ### 1.Line Plot
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()
#7.Boxplot
plt.boxplot(x="Sales",data=df)
plt.show()

![image](https://user-images.githubusercontent.com/112244898/236746758-c428db4f-d256-4b64-b7c0-2908775d7359.png)
1.LINE PLOT
![image](https://user-images.githubusercontent.com/112244898/236746843-f02e6101-694e-45b4-85ee-7cbda08996fe.png)

![image](https://user-images.githubusercontent.com/112244898/236746873-2a8c97b4-9254-4ef0-b83a-3fdcbc43c045.png)

![image](https://user-images.githubusercontent.com/112244898/236746896-18e47722-2263-4114-bb66-c62e5530097c.png)

2.SCATTER PLOT
![image](https://user-images.githubusercontent.com/112244898/236746944-a9ae23a2-8849-413f-90be-fe4828192ef5.png)

![image](https://user-images.githubusercontent.com/112244898/236746976-2f825608-d8c3-47f8-914a-be27c4e0c76c.png)

![image](https://user-images.githubusercontent.com/112244898/236747001-933ef10b-635d-4c33-b102-617b2c17ed38.png)

3.BOX PLOT

![image](https://user-images.githubusercontent.com/112244898/236747058-26e1bdad-daae-4d92-90e3-c0dcc6a382c6.png)

![image](https://user-images.githubusercontent.com/112244898/236747082-31b86cee-ae57-48e5-812c-906c733496c3.png)

4.VIOLIN PLOT

![image](https://user-images.githubusercontent.com/112244898/236747125-961b4fc6-4a37-41ba-aacf-4e7776cfc278.png)

5.BAR PLOT
![image](https://user-images.githubusercontent.com/112244898/236747188-8c24b284-ed10-468b-9231-0fef012a4ea4.png)

![image](https://user-images.githubusercontent.com/112244898/236747221-aa6da4f5-bcdd-4d72-966c-667d72298d42.png)

6.POINT PLOT

![image](https://user-images.githubusercontent.com/112244898/236747283-3d1a017c-7638-4de9-b663-431b21776905.png)

7.COUNT PLOT

![image](https://user-images.githubusercontent.com/112244898/236747332-4a58de7a-72bd-4543-ae89-8c0072f1720e.png)

![image](https://user-images.githubusercontent.com/112244898/236747352-83a5b401-9180-4e47-bc8e-350d54db2232.png)

8.HISTOGRAM

![image](https://user-images.githubusercontent.com/112244898/236747403-2d3ac5d2-4e0b-4fb5-ae4e-61146e7b5b7f.png)

9.KDE PLOT

![image](https://user-images.githubusercontent.com/112244898/236747468-f5b37339-ae87-4569-b7f4-1bbbbd7bbc4c.png)

Data Visualization Using Matplotlib:

1.Plot

![image](https://user-images.githubusercontent.com/112244898/236747593-2de95687-2e0e-403a-9fb5-a9acb01e4f31.png)

2.HEAT MAP

![image](https://user-images.githubusercontent.com/112244898/236747640-b92d9362-7e10-4de9-a89a-6d6337658a52.png)

3.Piechart

![image](https://user-images.githubusercontent.com/112244898/236747692-c19f7401-46ff-4d43-852d-c180951f4c80.png)

![image](https://user-images.githubusercontent.com/112244898/236747716-04c85460-7634-4b73-b4f6-f70af929f86d.png)

4.HISTOGRAM

![image](https://user-images.githubusercontent.com/112244898/236747761-8451b54b-38f3-44ed-b9f7-666eeb159d84.png)

5.BAR GRAPH

![image](https://user-images.githubusercontent.com/112244898/236747799-6d12bb2c-aa5d-4481-95cf-9ea599a371ad.png)

6.SCATTER PLOT 

![image](https://user-images.githubusercontent.com/112244898/236747850-814ec67c-a1c5-49c2-afcc-1ece6cde6584.png)

7.BOXPLOT

![image](https://user-images.githubusercontent.com/112244898/236747898-52e586df-b2f4-4f7e-87f1-9d0cb2481530.png)

RESULT
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

