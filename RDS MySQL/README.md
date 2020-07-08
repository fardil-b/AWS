# Connectiong to RDS Instance via Workbench
## Create MySQL database from Amazon RDS and use it from MySQL Workbench

## Go to Amazon RDS Console
![image](https://user-images.githubusercontent.com/61830624/86850131-0bec4780-c0b1-11ea-820d-f60a1ac318a1.png)

## Create MySQL Database
![image](https://user-images.githubusercontent.com/61830624/86850724-13602080-c0b2-11ea-8830-8c120026047a.png)

## Select yes for public access since we want to connect to workbench
![image](https://user-images.githubusercontent.com/61830624/86852434-0c86dd00-c0b5-11ea-9f6e-90f91836f2ae.png)

## Once created go to VPC security groups
![image](https://user-images.githubusercontent.com/61830624/86854050-ffb7b880-c0b7-11ea-9827-470b77a06be8.png)

## Edit inbound rules
![image](https://user-images.githubusercontent.com/61830624/86856224-2b3ca200-c0bc-11ea-8100-064285b82709.png)

## Download MySQL Workbench
![image](https://user-images.githubusercontent.com/61830624/86857336-94bdb000-c0be-11ea-94db-98e40d5b45b2.png)

## Click on the + next to MySQL Connections
![image](https://user-images.githubusercontent.com/61830624/86859143-47dbd880-c0c2-11ea-957d-1f25a238df86.png)

## Use information for the database from RDS AWS 
![image](https://user-images.githubusercontent.com/61830624/86861318-1dd8e500-c0c7-11ea-94f9-de1f31fde5d3.png)

## Fill the the endpoint info and enter the password we put at set up
![image](https://user-images.githubusercontent.com/61830624/86861178-bcb11180-c0c6-11ea-9727-e0fa92e7cf20.png)

## Click to MySQL Connection (s20-mysql)
![image](https://user-images.githubusercontent.com/61830624/86861468-7c05c800-c0c7-11ea-8594-08f33b19b97e.png)

## create a new schema
![image](https://user-images.githubusercontent.com/61830624/86861718-01897800-c0c8-11ea-9e9c-fa71e6db0d7a.png)

## create a new table
![image](https://user-images.githubusercontent.com/61830624/86862000-a015d900-c0c8-11ea-85d2-d1cb1df85700.png)

## We inserted some data
![image](https://user-images.githubusercontent.com/61830624/86862531-aa84a280-c0c9-11ea-9cb3-b3f5f390927d.png)

## Let retrieve the data from the table
![image](https://user-images.githubusercontent.com/61830624/86862885-6940c280-c0ca-11ea-923d-29fc5f5c761d.png)
#This shows that we were able to connect to our database instance because:
* It was accessible publicly
* We were able to connect to this database instance using it's endpoint 
* All this was posilbe because we configure the security group to allow the communication 
