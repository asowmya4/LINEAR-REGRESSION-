# LINEAR-REGRESSION-
Linear Regression assumes a linear relationship between the input variables ( 𝑥 x) and the output variable ( 𝑦 y). The goal is to find the line (or hyperplane in multiple dimensions) that best fits the data, minimizing the difference between the predicted and actual values.
The general equation for linear regression is:  y=mx+c(for simple linear rgression )
                                                y=β0+β1x1+.......βnxn+ϵ(for multiple linear regression )
Steps in Linear Regression
Data Preprocessing:
Ensure data is clean (no missing or irrelevant values).
Scale features if necessary.
Model Training:
Fit a regression model to the training data to learn the coefficients.
Evaluation:
Use metrics like Mean Squared Error (MSE), R-squared (R2), to evaluate the model's performance.
Prediction:
Use the model to predict the target variable for new data.

code for the linear regression :
#linear regression
import pandas as pd
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
data=pd.read_csv("sal.csv")
x=data.iloc[:,0].values.reshape(-1,1)
y=data.iloc[:,1].values.reshape(-1,1)
model=LinearRegression()
x_train, x_test, y_train, y_test = train_test_split(data.iloc[:, 0].values.reshape(-1, 1),  data.iloc[:, 1].values,test_size=0.1,random_state=42)
model.fit(x_train.reshape(-1,1),y_train)
print(model.intercept_,model.coef_)

output:4.997937351630959 [0.83203337]

from sklearn.metrics import mean_absolute_error,mean_squared_error
y_pred=model.predict(x_test)
mae=mean_absolute_error(y_test,y_pred)
maf=mean_squared_error(y_test,y_pred)
print(mae)
print(maf)

output:3.995962440519061
25.092610605091192
