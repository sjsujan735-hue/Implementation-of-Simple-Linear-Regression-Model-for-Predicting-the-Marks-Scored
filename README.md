# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

 
 1. Load the dataset into a DataFrame and explore its contents to understand the data structure.

 2.Separate the dataset into independent (X) and dependent (Y) variables, and split them into training and testing sets.

 3.Create a linear regression model and fit it using the training data.

 4.Predict the results for the testing set and plot the training and testing sets with fitted lines.

 5.Calculate error metrics (MSE, MAE, RMSE) to evaluate the model’s performance.

## Program:
```
/*
Program to implement univariate Linear Regression to fit a straight line using least squares.
Developed by: SUJAN S
RegisterNumber: 212225220108

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error,mean_squared_error
df=pd.read_csv('student_scores.csv')
print(df)

print(df.head())
print(df.tail())

x = df.iloc[:,:-1].values
print(x)
y = df.iloc[:,1].values
print(y)

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(x_train,y_train)
y_pred = regressor.predict(x_test)
print(y_pred)
print(y_test)

#Graph plot for training data
plt.scatter(x_train,y_train,color='black')
plt.plot(x_train,regressor.predict(x_train),color='blue')
plt.title("Hours vs Scores(Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()

#Graph plot for test data
plt.scatter(x_test,y_test,color='black')
plt.plot(x_train,regressor.predict(x_train),color='red')
plt.title("Hours vs Scores(Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_absolute_error(y_test,y_pred)
print('MSE = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print('MAE = ',mae)
rmse=np.sqrt(mse)
print("RMSE= ",rmse)
```

## Output:
# Dataset:
<img width="207" height="335" alt="image" src="https://github.com/user-attachments/assets/5a7da763-08ca-45f3-9fb7-e096fa3566f4" />
# Values:
<img width="343" height="242" alt="image" src="https://github.com/user-attachments/assets/247b4dba-a26d-49c3-8fdb-601c4366f61d" />
# Training set:
<img width="493" height="375" alt="image" src="https://github.com/user-attachments/assets/40517ae4-873d-404a-9bf9-3050b3009341" />
# Testing and MSE,MAE and RMSE:
<img width="526" height="446" alt="image" src="https://github.com/user-attachments/assets/55d81243-d74f-4eb6-97d5-f17662301f39" />








## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
