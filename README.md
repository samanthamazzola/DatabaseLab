# DatabaseLab
******tables, ER. written SQL/SQL server, queries via windows parallels*********




--SELECT distinct city from Customers
--ORDER BY city desc;


--WHERE comparing, inclusions, OR
--SELECT * from Customers
--WHERE city = 'paris' or city = 'london';
	--other way to include multiple cities
--SELECT * from Customers WHERE city in ('paris','london','berlin');


--COUNT you only want how many, not the data
--SELECT count(*) from Customers
--WHERE City in ('paris','london','berlin');


--AS keyword (names columns) after you SELECT what you want
--SELECT avg(UnitPrice) as 'Unit Price Avg', min(UnitPrice) as 'Unit Price Min', 
--max(UnitPrice) as 'Unit Price Max' --show what columns we want

--from Products; --the table you want in the db...from where



--datatype is BIT where 1 (which is true) or 0 (which is false)
--SELECT * from Products
--WHERE Discontinued = 1;


--GROUP BY
--SELECT SupplierID as 'Supplier ID', avg(UnitPrice) as 'Avg Unit Price'
--from Products
--group by SupplierID;


-- > or <  for range can be nums or dates
--SELECT * from Products
--WHERE UnitPrice >= 20 and UnitPrice <= 40;
	--OR
--SELECT * from Products
--WHERE UnitPrice between 20 and 40;


--GETDATE() == today
--SELECT * from Employees
--WHERE HireDate between '1994-01-01' and GETDATE();


--SELECT DATEDIFF(year, '2017/08/25', '2011/08/25') AS DateDiff
--from Employees;


--show all employee firstname and lastname and show how many years worked
--SELECT FirstName, LastName , DATEDIFF(year, HireDate, GetDate()) as 'Years Worked'
--from Employees;
	--ALSO 
--show all employee info and include how many years worked
--SELECT DATEDIFF(year, HireDate, GetDate()) as 'Years Worked', * from Employees;


--LIKE and WILDCARD.... % and _ for finding specific chars 
--SELECT * from Employees
--WHERE notes like '%university%';


--JOINS 
--show ORDERS where the value is NULL/ means they don't have an order
--SELECT Customers.CustomerID
--FROM Customers 
--LEFT JOIN Orders on Customers.CustomerId = Orders.CustomerID
--WHERE Orders.CustomerID is Null;
--ORDER BY Customers.CustomerID asc
	--OR right join... it just depends how you order the tables in the query
--SELECT Customers.CustomerID
--FROM Orders 
--RIGHT JOIN Customers on Customers.CustomerId = Orders.CustomerID
--WHERE Orders.CustomerID is Null;
--ORDER BY Customers.CustomerID asc


--DML INSERT STATEMENT
--INSERT INTO Customers(CustomerID, CompanyName)
--values ('QLINC','Quicken Loans Inc');

--DB VALIDATION using a SELECT statement
--SELECT * from Customers
--WHERE CustomerID = 'QLINC';


--UPDATE/SET
--UPDATE Customers
--set city = 'Detroit';
	--execute your update
	--SELECT ContactName, Address from Customers
	--WHERE city = 'detroit';


--UPDATE city for people with the custID of 'qlinc'
--set city = 'Detroit'
--WHERE CustomerID = 'QLINC';
	--deletes the customer you updated with the city 'Det' from your db
--DELETE Customers
--WHERE CustomerID = 'QLINC';
	--trying to delete something that is dependant on other data. 
	--if you wanted to delete that custID 'ALFKI', you must delete order first, then customer
		--cannot delete this customer because they have dependants/ they have an order...
		--DELETE Customers
		--WHERE CustomerID = 'alfki'; 



















