# EXPERIMENT NO: 8
# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn
### NAME : AVINASH T
### REG NO: 212223230026
## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics.
10. Find the accuracy of our model and predict the require values.

## Program & Output:
```c
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: AVINASH T
RegisterNumber: 212223230026
import pandas as pd
data = pd.read_csv("/content/Employee (1).csv")
data
```
![image](https://github.com/user-attachments/assets/15c93649-751e-48c2-bd3b-1e4ea6aac083)
```c
data.head()
```
![image](https://github.com/user-attachments/assets/be3eafd4-fcac-486a-a657-3625927bff99)
```c
data.info()
```
![image](https://github.com/user-attachments/assets/6e7ff0be-1838-4ac3-a3ac-f64d32186ab9)
```c
data.isnull().sum()
data["left"].value_counts
from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
![image](https://github.com/user-attachments/assets/2e19fe13-9955-49ee-a273-f6d110cae0c0)
```c
x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
```
![image](https://github.com/user-attachments/assets/9315a82d-f0ac-4ecc-9e79-2588eb1a7e2f)
```c
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)
from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy
```
![image](https://github.com/user-attachments/assets/27525e85-71eb-4544-87d0-d36280f79fc6)
```c
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```
![image](https://github.com/user-attachments/assets/8856af6f-2b4e-4073-9983-4c6333a94648)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
