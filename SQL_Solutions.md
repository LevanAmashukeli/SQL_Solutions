# SQL_Solutions

1) 
SELECT 
	role 					AS "Role",
	max(salary) 			AS "Max Salary"
FROM Employees
GROUP BY role;

---------------------------

2)
SELECT 
	name 					AS "Employee Name",
	surname 				AS "Employee Surname",
	role 					AS "Role",
	max(salary) 			AS "Max Salary"
FROM Employees
GROUP BY role;

---------------------------

3)
SELECT 
	role           			AS  "Role",
	SUM(salary)    			AS  "Salary"
FROM Employees
GROUP BY role 
HAVING salary BETWEEN 300 AND 600;

---------------------------

4)
SELECT 
	pl.Name 	   			AS  "PriceList",
 	COUNT(pp.ProductId) 	AS  "DublicatesCount"  
FROM PriceList pl, PriceListProducts pp
WHERE pl.PriceListId = pp.PriceListProductId
GROUP BY pp.PriceListId

---------------------------

5)
SELECT 
	pp.PriceListId  		AS  "Price List",
	pp.Name  				AS  "Product Name",
	COUNT(pp.PriceListId) 	AS  "DublicatesCount"  
FROM PriceList pl, PriceListProducts pp
WHERE pl.PriceListId = pp.PriceListProductId
GROUP BY pp.PriceListId
