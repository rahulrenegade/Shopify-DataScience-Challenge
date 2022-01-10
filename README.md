# Shopify_DS_Challenge
Data Science challenge by Shopify
**SOLUTIONS:**

**Ways to solve the problem:**

a)	The AOV value after calculation is highly skewed because of the outliers present in the data. First, we need to verify this data with the records, so that they are entered correctly and there isn’t any error. If they are verified as legit, then we can say, these outliers are nothing but from the customers placing bulk orders. One of the ways to deal with this is to remove those outliers and calculate AOV, but before them we need to compare this given month’s data with rest of the months to check if these outliers/bulk orders are common in every month. If they are not common and only present in this month’s data, they can be removed to calculate the mean value. If they are common in every month’s data and the data is getting affected by these outliers then, we need to consider alternative aggregate function such as median for the given data.
b)	Median.
c)	$308.8898


**Question: -2**

a)

**Code:**

SELECT count(*) 
FROM [Orders] o 
inner join shippers s on o.shipperId = s.shipperid
where shippername ='Speedy Express'

**OUTPUT:**

Number of Records: 1
Expr1000
54

 

b)

**Code:**

SELECT count(lastName), lastName 
FROM [Employees] e 
inner join orders o on e.employeeId=o.employeeId 
group by  lastName

**Output:**

Expr1000    lastName
  11        Buchanan
  27        Callahan
  29        Davolio
  6         Dodsworth
  20        Fuller
  14        King
  31        Leverling
  40        Peacock
  18        Suyama
  
   
c)

**Code:**

select count(p.productId), p.productName 
from products p inner join orderdetails o on p.productId = o.productId 
inner join suppliers s on s.supplierId= p.supplierId 
where country='Germany' 
group by p.productId 
order by count(p.productId) desc limit 1

**Output:**

Number of Records: 1
count(p.productId)        ProductName
10                        Rössle Sauerkraut

