# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries.
2. Upload the dataset and check for any null values using .isnull() function.
3. Import LabelEncoder and encode the dataset.
4. Import DecisionTreeRegressor from sklearn and apply the model on the dataset.
5. Predict the values of arrays.
6. Import metrics from sklearn and calculate the MSE and R2 of the model on the dataset.
7. Predict the values of array.
8. Apply to new unknown values.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Santhana Lakshmi k
RegisterNumber: 212222240091
*/
```
```
import pandas as pd
data = pd.read_csv("/content/Salary (2).csv")
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/81e1d3a0-e34a-4cf1-baa5-5bc8231087b8)
```
data.info()
```
## Output:
![image](https://github.com/user-attachments/assets/a33e268e-5306-4e74-a85f-b3129b6b84a1)
```
data.isnull().sum()
```
## Output:
![image](https://github.com/user-attachments/assets/d252a450-c058-4c50-91dc-887b3c4e4901)
```
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/5b642f34-1f40-497f-aba6-079bfef9ca27)
```
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
```
## Output:
![image](https://github.com/user-attachments/assets/bc713857-4110-4bdf-ba8d-9440874a96f7)
```
r2=metrics.r2_score(y_test,y_pred)
r2
```
## Output:
![image](https://github.com/user-attachments/assets/7f327634-6317-462d-9aac-960a76a1f9cd)
```
dt.predict([[5,6]])
```
## Output:
![image](https://github.com/user-attachments/assets/686b6a30-383c-487d-868c-0bc2e1573897)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
