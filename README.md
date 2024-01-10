# curd-application-in-aws-
regarding api calls , lambda functions etc 



1.create the dynamo db no sql databse table / product_inventary and product_id 
2.create the lambda function before 
3. for the lambda function ctrate the IAM role so that it can access the dynamo db and also the cloudwatch for the logs 
   go to iam / crteate role / lambda / add policy with cloudwatch full access + dynamo db full access / name = serverless api role / done 
4. GO to lambda / create function / 
        fname=serverless api / runtime =  python / select the serverless api role created alredy / create function 
        you can change the memory and the timer setting in the confugration 
5.create the api gateway to connect the every thing 
    create api /rest/ new api / Name=serverless api / endpoint regional / creete api  then 
    create resorces / resorse name = health / enable cors / crete resorce /  
    same crete the another two resorses naem product and products 
    Now in the health resorce crete the method name as get / lambs function / use lambda proxy intigration / region and lambda function name / save 
    now in the product resorse = use the same process above and crete get , post, patch, delete
    now in the products session crete get method 
    then go to action /deploy/stage = dev / prod / deploy 
    now we hav ethe new stage prod and also the enpoint for the api 
6.Go to the lambda function then add the new functional code in the code 
7. Then copy the url from the api gateway and then open postman 
8.in the postman get = utl/ health send then if 200 responce means api is up and running then
  post /url/product then in body then in raw and json {
                                                       ...."productid": "100",
                                                       ...."colour":"red"
                                                       ...."price":100 
                                                       }
      send then it is successful 
9. Go to the database then you can see the data inside the tables 
10.

1. create the databse as dynamo db
2. create iam role with cloudwatch and the 


routing fixing 1.api gateway 
               2.webhook url hit lamda function 
               3.tenent unique or namespaces in diffrent database 
               4.connection end 
               5.for preventing that = service constant connect to database apply sqs (prpduct ans storage )
               6.load more maximum scale == back presure / geo logation  eg uber  to prevent this cutoff to prevent the data loss 
               7.

               8. mfk = amazon version always previous than current version 
               9. 

