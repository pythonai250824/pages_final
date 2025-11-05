# Tasks
## Phase 1
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

## Phase 2
1. add model KNN (like in phase 1)  
   change endpoint -- "create/lineraregression", and "predict/lineraregression"  
   change endpoint -- "create/knn", and "predict/knn"  
3. Create Postgresql database for the project -- should be saved as queries : create table queries, insert queries  
   in the DB, create ml_user table : id (autoincrement), email (unique) , pwd (at least 4 characters) , tokens  
   all db-connection data (+passwords) should be in separate file (not in py file)
   also upload to Github a few demos csv files for train (not related to database)     
5. create endpoint -- "user/create" which gets user email + pwd and creates a new user with 15 tokens   
6. create endpoint -- "user/login" which gets user email + pwd and validate -- return "OK" if correct or "FAIL" if not  
7. create streamlit page for creation of new user, calls REST API  
8. create streamlit page for login of a user, calls REST API    

## BONUS
- create python script that asks you the db connection data and runs the sql queries (i.e. create table if not exists ...)  
   
