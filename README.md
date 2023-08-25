# kreativebi2
# Data Analysis with SQL: Inform a Business Decision
#In this project, we will work with the Northwind Traders database, which contains data for the fictitious company Northwind Traders. Our task will be to pull data from the database to answer the question “Which Northwind Traders employees should get bonuses for their sales performance?”

![image](https://github.com/kirankampli/kreativebi2/assets/143105817/aa28183e-d551-4f9c-8ae7-648ac19c1920)

![image](https://github.com/kirankampli/kreativebi2/assets/143105817/a24b0200-f772-4b41-a68c-3e75e2ee6fd3)

![image](https://github.com/kirankampli/kreativebi2/assets/143105817/d194e31a-3d6f-4b25-9a14-2a2d65cbc171)

![image](https://github.com/kirankampli/kreativebi2/assets/143105817/8edfde76-3163-4a38-97af-43bc8bae1a49)





![image](https://github.com/kirankampli/kreativebi2/assets/143105817/ed1d4bc7-734f-4b84-97c1-0c987f634efc)
![image](https://github.com/kirankampli/kreativebi2/assets/143105817/3dd03cc9-128a-4f96-a9f5-e6b0b9f14b0f)

![image](https://github.com/kirankampli/kreativebi2/assets/143105817/0de830c8-b550-4969-9028-b0530ef3eba5)
![image](https://github.com/kirankampli/kreativebi2/assets/143105817/3eae7511-702a-4705-97d1-116ff37fb4d7)




Select Lastname, Firstname, Orders.OrderId, Products.ProductId, 
from employees
 inner join Orders 
  on Employees.EmployeeId= orders.EmployeeID

  ![image](https://github.com/kirankampli/kreativebi2/assets/143105817/94107c51-e98e-4767-adb0-082288c954d8)

Select Lastname, Firstname, Orders.OrderId, Products.ProductId, 
Quantity, Price
from employees
 inner join Orders 
  on Employees.EmployeeId= orders.EmployeeID
 inner join OrderDetails 
  on Orders.OrderId=OrderDetails.OrderID
 Order by Lastname, Firstname 

  ![image](https://github.com/kirankampli/kreativebi2/assets/143105817/483f3721-7448-4328-afb1-a5080fab2b61)

# Calculating and summarizing (aggregating the data using SQL functiuon Sum()  ) Sales for each order
Select Lastname, Firstname, Orders.OrderId, Products.ProductId, 
Quantity, Price, Sum(quantity*price) as Salesamt
from employees
 inner join Orders 
  on Employees.EmployeeId= orders.EmployeeID
 inner join OrderDetails 
  on Orders.OrderId=OrderDetails.OrderID
 Order by Lastname, Firstname
 
![image](https://github.com/kirankampli/kreativebi2/assets/143105817/e91f9fef-92f1-4549-978b-306b2aa919e6)


#  Grouping the data by using Group By clause and Ordering the Salesamt in the highest cronology and limiting them by top five Orders
  
Select Lastname, Firstname, Orders.OrderId, Products.ProductId, 
Quantity, Price, Sum(quantity*price) as Salesamt
from employees
 inner join Orders 
  on Employees.EmployeeId= orders.EmployeeID
 inner join OrderDetails 
  on Orders.OrderId=OrderDetails.OrderID
 Inner join Products
  on OrderDetails.ProductId=Products.ProductId
Group by Orders.OrderId
Order by salesamt Desc
Limit 5

![image](https://github.com/kirankampli/kreativebi2/assets/143105817/d1d6229f-51cf-4f46-9c1d-0411f3df3736)











