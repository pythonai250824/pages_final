# Tasks
## Linear Regression  
write funciton:  
gets as parameter a csv file name, name of feature columns, name of label column, train-test percentage, model-file-name  
also get as parameter the dict for each type of column, use get-dummies on string columns, date column should be parsed    
the function will create the LinearRegression model save the model into a file
also save the accuracy factors into a file  
[add something if needed]  

try training the model with few different output  

## REST API  
create fastAPI + swagger  
create endpoint "/create" which gets the function input and invoke the function  
create endpoint "/predict" which gets set of features + load the model from the file + predict with the model and return the result  
use swagger to invoke  
use POSTMAN to invoke the functions  

## BONUS
- invoke the rest api from python code  
- invoke the rest api from a streamlit page  



   
