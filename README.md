# Datawarehousing-Basics
SQL Query Practices with comments and output- log files.

2024-01-28 23:53:30.554875root[root] @ localhost [::1]91Query#40 \
SELECT /* ++A20529733 ++SQL040 */
\
p.Name \
FROM Product AS p
\
INNER JOIN SalesOrderDetail AS sod
\
ON p.ProductID = sod.ProductID
\
ORDER BY p.Name LIMIT 0
2024-01-28 23:51:25.637462root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL039 */ \
p.Name
\
FROM Product AS p
\
LEFT OUTER JOIN SalesOrderDetail AS sod
\
ON p.ProductID = sod.ProductID
\
ORDER BY p.Name LIMIT 0
2024-01-28 23:44:29.741267root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL037 */ \
Name
\
FROM Product
\
WHERE Color = 'Red'
\
UNION ALL
\
SELECT Name
\
FROM Product
\
WHERE Color = 'Blue'
\
ORDER BY ListPrice ASC LIMIT 0
2024-01-28 23:42:16.308848root[root] @ localhost [::1]91Query#35
\
SELECT /* ++A20529733 ++SQL035 */
\
DepartmentID
\
FROM Department LIMIT 0
2024-01-28 23:39:40.705054root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL034 */ \
DepartmentID
Page 1

\
FROM Department LIMIT 0
2024-01-28 23:39:33.508866root[root] @ localhost [::1]91Query#34
\
SELECT /* ++A20529733 ++SQL034 */
\
DepartmentID
\
FROM Department LIMIT 0
2024-01-28 23:38:50.764536root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL034 */ \
DepartmentID
\
FROM Department LIMIT 0
2024-01-28 23:38:46.002650root[root] @ localhost [::1]91Query#34
\
SELECT /* ++A20529733 ++SQL034 */
\
DepartmentID
\
FROM Department LIMIT 0
2024-01-28 23:35:22.622750root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL033 */ \
sp.BusinessEntityID
\
FROM person as ps
\
Inner join salesperson as sp
\
ON ps.BusinessEntityID = sp.BusinessEntityID
\
Inner join salesterritory AS st
\
ON st.territoryID=sp.territoryID
\
WHERE TerritoryName IS NOT NULL
\
ORDER BY
\
CASE CountryRegionName WHEN 'United States' THEN TerritoryName
\
ELSE CountryRegionName END LIMIT 0
2024-01-28 23:17:31.840595root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL033 */ \
BusinessEntityID
\
FROM SalesPerson
\
WHERE TerritoryName IS NOT NULL
\
ORDER BY
Page 2

\
CASE CountryRegionName WHEN 'United States' THEN TerritoryName
\
ELSE CountryRegionName END LIMIT 0
2024-01-28 23:12:56.674936root[root] @ localhost [::1]91Query#32
\
SELECT /* ++A20529733 ++SQL032 */
\
BusinessEntityID
\
FROM Employee
\
ORDER BY
\
CASE SalariedFlag WHEN 'true' THEN BusinessEntityID END DESC
\
CASE WHEN SalariedFlag ='false' or salariedflag = '0' THEN BusinessEntityID END LIMIT 0
2024-01-28 23:11:06.676939root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL032 */
\
BusinessEntityID
\
FROM Employee
\
ORDER BY
\
CASE SalariedFlag WHEN 'true' THEN BusinessEntityID END DESC
\
CASE WHEN SalariedFlag ='false' THEN BusinessEntityID END LIMIT 0
2024-01-28 23:10:33.924330root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL032 */
\
BusinessEntityID
\
FROM Employee
\
ORDER BY
\
CASE SalariedFlag WHEN 'true' THEN BusinessEntityID END DESC
\
CASE WHEN SalariedFlag ='false' THEN BusinessEntityID END ASC LIMIT 0
2024-01-28 23:04:31.144807root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL031 */ LastName \
FROM Person
\
WHERE LastName LIKE 'R%'
\
ORDER BY FirstName ASC
2024-01-28 23:02:22.959563root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL030 */
\
BusinessEntityID
\
FROM Employee
Page 3

\
ORDER BY year(HireDate) LIMIT 0
2024-01-28 22:57:46.112331root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL030 */BusinessEntityID \
FROM Employee
\
ORDER BY DATE_PART('year'
2024-01-28 22:43:32.529675root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL029 */ ProductID
\
FROM Product
\
ORDER BY ListPrice LIMIT 0
2024-01-28 22:40:16.979654root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL028 */ ProductID
\
FROM Product
\
WHERE Name LIKE 'Lock Washer%'
\
ORDER BY ProductID asc LIMIT 0
2024-01-28 22:28:42.481475root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL027 */ SalesOrderID
\
FROM SalesOrderDetail
\
GROUP BY SalesOrderID
\
HAVING sum(orderqty*unitprice) > 100000.00
\
ORDER BY SalesOrderID LIMIT 0
2024-01-28 22:28:29.559802root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL027 */ SalesOrderID
\
FROM SalesOrderDetail
\
GROUP BY SalesOrderID
\
HAVING (orderqty*unitprice) > 100000.00
\
ORDER BY SalesOrderID LIMIT 0
2024-01-28 21:19:31.156691root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL022 */
\
pc.ContactTypeID \
FROM BusinessEntityContact AS pbe \
INNER JOIN ContactType AS pc \
ON pc.ContactTypeID = pbe.ContactTypeID \
GROUP BY pc.ContactTypeID \
HAVING COUNT(*) >= 100 \
Page 4

ORDER BY COUNT(*) DESC LIMIT 0
2024-01-28 21:18:48.714555root[root] @ localhost [::1]91QuerySelect /* ++A20529733 ++SQL022 */
\
be.contacttypeid
\
FROM BusinessEntityContact AS be
\
Inner join ContactType AS ct
\
ON be.contacttypeid = ct.contacttypeid
\
GROUP BY pc.ContactTypeID
\
HAVING Count(*) >= 100
\
ORDER BY COUNT(*) DESC LIMIT 0
2024-01-28 21:11:02.274832root[root] @ localhost [::1]91Query#22
\
Select /* ++A20529733 ++SQL022 */
\
be.contacttypeid
\
FROM BusinessEntityContact AS be
\
Inner join ContactType AS ct
\
ON be.contacttypeid = ct.contacttypeid
\
HAVING Count(*) >= 100
\
ORDER BY Nocontacts DESC LIMIT 0
2024-01-28 21:10:48.853070root[root] @ localhost [::1]91QuerySelect /* ++A20529733 ++SQL022 */
\
be.contacttypeid
\
FROM BusinessEntityContact AS be
\
Inner join ContactType AS ct
\
ON be.contacttypeid = ct.contacttypeid
\
WHERE Count(*) >= 100
\
ORDER BY Nocontacts DESC LIMIT 0
2024-01-28 21:03:12.784912root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL021 */ ROW_NUMBER() OV \
pp.LastName \
FROM SalesPerson AS sp \
INNER JOIN Person AS pp
Page 5

\
ON sp.BusinessEntityID = pp.BusinessEntityID
\
INNER JOIN Address AS pa
\
ON pa.AddressID = pp.BusinessEntityID
\
WHERE TerritoryID IS NOT NULL \
AND SalesYTD <> 0 \
WINDOW win AS (PARTITION BY PostalCode ORDER BY SalesYTD DESC)
\
ORDER BY PostalCode LIMIT 0
2024-01-28 20:56:56.632294root[root] @ localhost [::1]91QuerySelect /* ++A20529733 ++SQL021 */ \
ROW_NUMBER() OVER win AS "Row Number" \
FROM salesperson AS sp \
Inner join person AS pp
\
ON pp.BusinessEntityID = sp.BusinessEntityID \
INNER Join address as ad
\
ON ad.rowguid = sp.rowguid
\
WHERE TerritoryID IS NOT Null \
AND SalesYTD <> 0
\
ORDER BY PostalCode LIMIT 0
2024-01-28 20:56:13.024743root[root] @ localhost [::1]91QuerySelect /* ++A20529733 ++SQL021 */ \
rownumber
\
FROM salesperson AS sp
\
Inner join person AS pp
\
ON pp.BusinessEntityID = sp.BusinessEntityID
\
INNER Join address as ad
\
ON ad.rowguid = sp.rowguid
\
WHERE TerritoryID IS NOT Null
\
AND SalesYTD <> 0
\
Page 6

ORDER BY PostalCode LIMIT 0
2024-01-28 18:45:24.529599root[root] @ localhost [::1]91QuerySELECT /* ++A20529733 ++SQL001 */
\
*
\
FROM employee
\
ORDER BY jobtitle ASC LIMIT 0
2024-01-21 23:28:12.962648root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL020 */ \
pp.BusinessEntityID \
FROM BusinessEntityContact AS pb \
INNER JOIN ContactType AS pc
\
ON pc.ContactTypeID = pb.ContactTypeID \
INNER JOIN Person AS pp
\
ON pp.BusinessEntityID = pb.PersonID
\
WHERE pc.Name = 'Purchasing Manager' \
ORDER BY LastName
2024-01-21 23:24:26.583658root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL019 */ \
ContactTypeID
\
FROM ContactType
\
WHERE NAME LIKE '%Manager%'
\
ORDER BY NAME DESC LIMIT 0
2024-01-21 23:23:23.362942root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL019 */ \
ContactTypeID \
FROM \
ContactType \
WHERE \
NAME LIKE '%Manager%' \
ORDER BY \
NAME DESC LIMIT 0
2024-01-21 23:05:52.642541root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL017 */ \
Page 7

DATEPART(YEAR \
SUM(TotalDue) AS "ORDER Amount" \
FROM \
SalesOrderHeader \
GROUP BY \
DATEPART(YEAR \
ORDER BY \
DATEPART(YEAR
2024-01-21 23:04:49.874144root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL017 */ \
DATEPART(YEAR \
SUM(TotalDue) AS "ORDER Amount" \
FROM \
SalesOrderHeader \
GROUP BY \
DATEPART(YEAR \
ORDER BY \
DATEPART(YEAR
2024-01-21 23:03:55.159097root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL017 */ \
DATE_PART('year' \
SUM(TotalDue) AS "ORDER Amount" \
FROM \
SalesOrderHeader \
GROUP BY \
DATE_PART('year' \
ORDER BY \
DATE_PART('year'
2024-01-21 22:48:58.428216root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL017 */ \
Page 8

DATE_PART('year' \
\
FROM SalesOrderHeader
\
GROUP BY DATE_PART('year'
\
ORDER BY DATE_PART('year'
2024-01-21 22:48:13.193905root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL017 */ \
DATE_PART('year'
\
\
FROM SalesOrderHeader
\
GROUP BY DATE_PART('year'
\
ORDER BY DATE_PART('year'
2024-01-21 22:47:32.772788root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL017 */ \
DATE_PART('year'
\
\
FROM SalesOrderHeader
\
GROUP BY DATE_PART('year'
\
ORDER BY DATE_PART('year'
2024-01-21 22:35:33.803173root[root] @ localhost [::1]121Query#16
\
SELECT /* ++A20529733 ++SQL016 */
\
a.City
\
FROM BusinessEntityAddress AS b
\
INNER JOIN Address AS a
\
ON b.AddressID = a.AddressID
\
GROUP BY a.City
\
ORDER BY a.City LIMIT 0
2024-01-21 22:28:42.062755root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL011 */ \
p.BusinessEntityID
\
FROM Person AS p
Page 9

\
JOIN PersonPhone AS ph
\
ON p.BusinessEntityID = ph.BusinessEntityID
\
WHERE p.LastName LIKE 'L%'
\
ORDER BY p.LastName
2024-01-21 22:26:23.579766root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL011 */ \
p.BusinessEntityID
\
FROM Person AS p
\
JOIN PersonPhone AS ph
\
ON p.BusinessEntityID = ph.BusinessEntityID
\
WHERE p.LastName LIKE 'L%'
\
ORDER BY p.LastName
2024-01-21 22:24:10.963824root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL011 */ \
BusinessEntityID
\
FROM Person AS p
\
JOIN PersonPhone AS ph
\
ON BusinessEntityID = BusinessEntityID
\
WHERE LastName LIKE 'L%'
\
ORDER BY LastName
2024-01-21 21:59:37.316832root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL011 */ \
BusinessEntityID
\
FROM Person AS p
\
JOIN PersonPhone AS ph
\
ON BusinessEntityID = BusinessEntityID
\
WHERE LastName LIKE 'L%'
\
ORDER BY LastName
2024-01-21 21:59:34.471775root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL011 */ \
BusinessEntityID
\
Page 10

FROM Person AS p
\
JOIN PersonPhone AS ph
\
ON BusinessEntityID = BusinessEntityID
\
WHERE LastName LIKE 'L%'
\
ORDER BY LastName
2024-01-21 21:59:13.184522root[root] @ localhost [::1]121Query#11
\
SELECT /* ++A20529733 ++SQL011 */
\
BusinessEntityID
\
FROM Person AS p
\
JOIN PersonPhone AS ph
\
ON p.BusinessEntityID = ph.BusinessEntityID
\
WHERE LastName LIKE 'L%'
\
ORDER BY LastName
2024-01-21 21:21:16.028957root[root] @ localhost [::1]121Query#9
\
SELECT /* ++A20529733 ++SQL009 */
\
PRODUCTID
\
from productinventory
\
where SHELF in ('A'
\
GROUP BY PRODUCTID
\
HAVING SUM(QUANTITY) > 500
\
ORDER BY PRODUCTID LIMIT 0
2024-01-21 21:19:26.274600root[root] @ localhost [::1]121QuerySELECT/* ++A20529733 ++SQL009 */ \
productid \
FROM productinventory \
WHERE shelf IN ('A'
\
GROUP BY productid
\
HAVING SUM(quantity)>500 \
Page 11

ORDER BY productid LIMIT 0
2024-01-21 21:17:49.017420root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL009 */ \
PRODUCTID
\
from productinventory
\
where SHELF in ('A'
\
GROUP BY PRODUCTID LIMIT 0
2024-01-21 21:16:27.551881root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL009 */ \
PRODUCTID
\
from productinventory
\
where SHELF in ('A'
\
AND SUM(QUANTITY) > 500
\
ORDER BY PRODUCTID LIMIT 0
2024-01-21 21:15:42.935363root[root] @ localhost [::1]121Query#9
\
SELECT /* ++A20529733 ++SQL009 */
\
PRODUCTID
\
from productinventory
\
where SHELF in ('A'
\
AND SUM(QUANTITY) > 500
\
ORDER BY PRODUCTID LIMIT 0
2024-01-21 21:15:13.098218root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL009 */ \
PRODUCTID
\
from productinventory
\
where SHELF in ('A'
\
AND SUM_QUANTITY > 500
\
ORDER BY PRODUCTID LIMIT 0
2024-01-21 21:13:21.997542root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL009 */ \
PRODUCTID
\
from productinventory
\
Page 12

where SHELF = 'A' OR 'C' OR 'H' \
AND SUM_QUANTITY > 500
\
GROUP BY PRODUCTID
\
ORDER BY PRODUCTID LIMIT 0
2024-01-21 21:12:30.790776root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL009 */ \
PRODUCTID
\
from productinventory
\
where SHELF = 'A' OR 'C' OR 'H'
\
AND SUM_QUANTITY > 500
\
GROUP BY PRODUCTID
\
ORDER BY PRODUCTID LIMIT 0
2024-01-21 20:56:43.439888root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL008 */ \
customerid
\
from salesorderheader
\
GROUP BY customerid
\
ORDER BY customerid desc LIMIT 0
2024-01-21 20:56:34.478824root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL008 */ \
customerid
\
from salesorderheader
\
\
ORDER BY customerid desc LIMIT 0
2024-01-21 20:56:01.367642root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL008 */ \
customerid
\
from salesorderheader
\
GROUP BY customerid
\
ORDER BY customerid desc LIMIT 0
2024-01-21 20:54:51.961339root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL008 */ \
salespersonid
\
from salesorderheader
Page 13

\
GROUP BY customerid
\
ORDER BY customerid desc LIMIT 0
2024-01-21 20:53:38.963673root[root] @ localhost [::1]121Query#8
\
SELECT /* ++A20529733 ++SQL008 */
\
customerid
\
from salesorderheader
\
GROUP BY avgsubtotal
\
ORDER BY customerid desc LIMIT 0
2024-01-21 20:38:14.044683root[root] @ localhost [::1]121Query#7
\
SELECT /* ++A20529733 ++SQL007 */
\
customerid
\
FROM salesorderheader
\
GROUP BY customerid LIMIT 0
2024-01-21 20:37:46.273901root[root] @ localhost [::1]121Query#7
\
SELECT /* ++A20529733 ++SQL007 */
\
customerid
\
FROM salesorderheader
\
\
ORDER BY customerid ASC LIMIT 0
2024-01-21 20:37:16.330598root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL007 */ \
customerid
\
FROM salesorderheader
\
GROup by customerid
\
ORDER BY customerid ASC LIMIT 0
2024-01-21 20:35:45.763545root[root] @ localhost [::1]121Query#7
\
SELECT /* ++A20529733 ++SQL007 */
\
customerid
\
FROM salesorderheader
\
Page 14

ORDER BY customerid ASC LIMIT 0
2024-01-21 20:13:39.982098root[root] @ localhost [::1]121QuerySELECt /* ++A20529733 ++SQL006 */ \
Distinct jobtitle
\
FROM employee
\
order by jobtitle ASC LIMIT 0
2024-01-21 20:08:04.899246root[root] @ localhost [::1]121Query#5
\
SELECT /* ++A20529733 ++SQL005 */
\
salesorderid
\
FROM salesorderheader
\
ORDER by subtotal LIMIT 0
2024-01-21 20:07:09.234572root[root] @ localhost [::1]121Query#5
\
SELECT /* ++A20529733 ++SQL005 */
\
salesorderid
\
FROM salesorderheader
\
ORDER by subtotal LIMIT 0
2024-01-21 20:06:49.765987root[root] @ localhost [::1]121Query#5
\
SELECT /* ++A20529733 ++SQL005 */
\
salesorderid
\
FROM salesorderheader
\
ORDER by subtotal LIMIT 0
2024-01-21 20:06:42.068500root[root] @ localhost [::1]121Query#5
\
SELECT /* ++A20529733 ++SQL005 */
\
salesorderid
\
FROM salesorderheader
\
ORDER by subtotal LIMIT 0
2024-01-21 19:58:15.204093root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
productid
\
FROm product
\
WHERE sellstartdate IS NOT NULL
Page 15

\
AND productline = 'T'
\
ORDER BY productname LIMIT 0
2024-01-21 19:56:21.871273root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
productid
\
FROm product
\
WHERE sellstartdate IS NOT NULL
\
AND productline = 'T' LIMIT 0
2024-01-21 18:39:50.794931root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
productid
\
FROm product
\
WHERE sellstartdate IS NOT NULL
\
AND productline = 'T' LIMIT 0
2024-01-21 18:38:28.302983root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
productid
\
FROm product
\
WHERE sellstartdate IS NOT NULL
\
AND productline = 'T' LIMIT 0
2024-01-21 18:36:55.515438root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
*
\
FROm product
\
WHERE sellstartdate IS NOT NULL
\
AND productline = 'T' LIMIT 0
2024-01-21 18:35:40.351010root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
*
\
FROm product
\
WHERE sellstartdate IS NOT NULL
\
AND productline = T LIMIT 0
2024-01-21 18:34:48.046961root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
Page 16

*
\
FROm product
\
WHERE sellstartdate IS NOT NULL
\
AND productline = T
\
ORDER BY name LIMIT 0
2024-01-21 18:34:23.112653root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL004 */ \
*
\
FROm products
\
WHERE sellstartdate IS NOT NULL
\
AND productline = T
\
ORDER BY name LIMIT 0
2024-01-21 18:24:33.864415root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL003 */ \
firstname
\
FROM person
\
ORDER BY lastname ASC LIMIT 0
2024-01-21 18:17:32.399364root[root] @ localhost [::1]121Query#2
\
SELECT duplicatetable.*/* ++A20529733 ++SQL002 */
\
FROM person
\
AS duplicatetable
\
ORDER BY lastname LIMIT 0
2024-01-21 18:13:32.367431root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL002 */ \
*
\
FROM person
\
AS duplicatetable
\
ORDER BY lastname LIMIT 0
2024-01-21 18:02:00.200572root[root] @ localhost [::1]121Query#2
\
SELECT /* ++A20529733 ++SQL002 */
\
*
\
Page 17

fROM employee
\
AS duplicatetable \
ORDER BY last_name LIMIT 0
2024-01-21 18:01:37.901674root[root] @ localhost [::1]121Query#2
\
SELECT /* ++A20529733 ++SQL002 */
\
*
\
fROM employee
\
AS duplicatetable
\
ORDER BY lastname LIMIT 0
2024-01-21 17:56:24.285497root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL001 */ \
*
\
FROM employee
\
ORDER BY jobtitle ASC LIMIT 0
2024-01-21 17:10:59.752883root[root] @ localhost [::1]121QuerySELECT /* ++A20529733 ++SQL001 */ \
*
\
FROM employee
\
ORDER BY jobtitle LIMIT 0
Page 18

sod.SalesOrderID
sod.SalesOrderID
Color
Color
ListPrice
ListPrice
name
name
1000
1000
GroupName
GroupName Page 19
1000
1000

name
name
name
ps.LastName
1000
1000
1000
GroupName
GroupName
GroupName
st.TerritoryName
LastName
TerritoryName
1000
1000
Page 20

SalariedFlag
SalariedFlag
SalariedFlag
FirstName
LastName DESC LIMIT 0 JobTitle
1000
1000
1000
1000
HireDate
Page 21
1000

JobTitle
HireDate) LIMIT 0 Name
Name
HireDate
Color
1000
1000 sum(orderqty*unitprice) AS OrderIDCost
1000 (orderqty*unitprice) AS OrderIDCost
pc.Name AS CTypeName
pc.Name
COUNT(*) AS NOcontacts
1000
1000
1000
Page 22

ct.name AS ContactTypeName
pc.Name
ct.name AS ContactTypeName
COUnt(*) AS Nocontacts
ct.name AS ContactTypeName
COUnt(*) AS Nocontacts
sp.SalesYTD
pa.PostalCode
1000
1000
1000
1000
COUnt(*) AS Nocontacts
Page 23

lastname
salesytd
lastname
salesytd
1000
1000
Page 24

LastName
FirstName
FirstName LIMIT 0 NAME
NAME
1000
1000
1000
1000
1000
Page 25

OrderDate)
AS "YEAR"
OrderDate)
OrderDate) OrderDate)
OrderDate)
OrderDate) OrderDate)
OrderDate)
OrderDate)
LIMIT 0
AS "YEAR"
1000
LIMIT 0
AS "YEAR"
1000
LIMIT 0
1000
Page 26

OrderDate) AS 'YEAR' SUM(TotalDue) AS 'ORDER Amount'
OrderDate) OrderDate) LIMIT 0
OrderDate) AS 'YEAR' SUM(TotalDue) AS "Order Amount"
OrderDate) OrderDate) LIMIT 0
OrderDate) AS "Year" SUM(TotalDue) AS "Order Amount"
OrderDate) OrderDate) LIMIT 0
COUNT(b.AddressID) NoOfEmployees
1000
p.FirstName
p.LastName
1000
Page 27
1000
1000

p.FirstName LIMIT 0 p.FirstName
p.FirstName LIMIT 0 FirstName
FirstName LIMIT 0 FirstName
FirstName LIMIT 0 FirstName
1000
p.LastName
LastName
LastName
LastName Page 28
1000
1000
1000

FirstName LIMIT 0
FirstName
FirstName LIMIT 0
SUM(QUANTITY) as SUM_QUANTITY
1000
'C'
sum(quantity) AS total_quantity
'C'
'H')
1000
LastName
'H')
Page 29
1000

1000 SUM(QUANTITY) as SUM_QUANTITY
'C' 'H') 1000
SUM(QUANTITY) as SUM_QUANTITY
'C' 'H')
1000
SUM(QUANTITY) as SUM_QUANTITY
'C' 'H')
1000 SUM(QUANTITY) as SUM_QUANTITY
'C'
SHELF
1000
'H')
SUM(QUANTITY) as SUM_QUANTITY
Page 30

1000 SUM(QUANTITY) as SUM_QUANTITY
salespersonid
salespersonid
salespersonid
salespersonid
salespersonid
avg(subtotal) as avg_subtotal
1000
1000
1000
1000
avg(subtotal) as avg_subtotal
avg(subtotal) as avg_subtotal
avg(subtotal) as avg_subtotal
sum(subtotal)AS sum_subtotal
Page 31

salespersonid
salespersonid
salespersonid
sum(Freight) AS totalfreight
sum(Freight) AS totalfreight
sum(Freight) AS totalfreight
avg(subtotal) as avgsubtotal
sum(freight) AS totalfreight
1000
1000
1000
1000
1000
Page 32

customerid
customerid
customerid
customerid
productnumber
1000
1000
1000
1000
1000
orderdate
orderdate
orderdate
orderdate
NAME AS productname
1000
Page 33

productnumber
productnumber
productnumber
1000
1000
1000
1000
1000
1000
NAME AS productname
NAME AS productname
NAME AS productname
Page 34

lastname
1000
1000
1000
1000
businessentityid AS Employee_id
1000
Page 35

1000
1000
1000
1000
Page 36

st.CountryRegionName
CountryRegionName
Page 37

postalcode
postalcode
Page 38

ph.PhoneNumber AS Person_Phone
Page 39

ph.PhoneNumber AS Person_Phone
PhoneNumber AS Person_Phone
PhoneNumber AS Person_Phone
PhoneNumber AS Person_Phone
Page 40

PhoneNumber AS Person_Phone
Page 41

UM_QUANTITY
Page 42

sum(subtotal)AS sum_subtotal
sum(subtotal)AS sum_subtotal
sum(subtotal)AS sum_subtotal
Page 43

sum(subtotal)AS sum_subtotal
Page 44

subtotal
subtotal
subtotal
subtotal
(taxamt*100)/subtotal AS Tax_percent
percentage(tax)
percentage(tax/subtotal)
Page 45

