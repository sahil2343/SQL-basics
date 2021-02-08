# Structured Query Language (SQL)
## About and History
**S**tructured **Q**uery **L**anguage is a standard language in relational database which is used to create, maintain, and retrieve data from database servers. It was first developed in **1970** and at that time it was known as **SEQUEL**.
___________
## Basics of SQL
### What is Relational Database?
Relational database means the data is stored and retrieved in the form of tables.
For dealing with the relational database, there are some queries that are needed to be perform in-order to fetch data.
1. **Data Definition Language (DDL)** :- In relational database, without table structured data, nothing can be done. So, DDL is used to create the structure of the database. Commands for e.g CREATE, ALTER, DROP e.t.c. are used.
2.  **Data Manipulation Language (DML)** :- It is used to manipulate data in the tables. Commands like SELECT, INSERT, DELETE, UPDATE e.t.c are used.
 _______________________________________
* **Create a table** :- CREATE TABLE TABLENAME( variables )
e.g ```CREATE TABLE Employee(Id int, Name varchar(20), Age int)```.
This command will create a table named Employee:-
* **Alter a table** :- ```ALTER TABLE Employee Add(Address varchar(30))```. This command will add a coloumn address to the table.
* **Insert into the table** :- ```INSERT INTO Employee 
VALUES(1, Pankaj, 30, SBP)```
Insert into the table :- ```INSERT INTO Employee VALUES(4, Roshan, 25, BBSR)```
* **Updating a row** :- ```UPDATE Employee SET Age = 26 WHERE Id = 4```

After all these commands were executed the table will look like :-

**Employee**
Id | Name | Age | Address
--- | ------- | ---- | ------
1|Pankaj|30|SBP
4|Roshan|26|BBSR
---------------
## JOINS IN SQL
### What are JOINS?
Suppose that we need to do a operation where data from more than 1 tables are required, one way to perform these tasks is to use joins. 
Generally, Join = Cross product (T1 * T2) + some conditions. **There should be **one common field** between them to perform these tasks. Different types of joins are :-
*  **Natural Join** :- The NATURAL JOIN keyword select all rows from both the tables as long as the given condition satisfies( value of common field matches). 

**Emp**

E_no | E_name | D_no
------ | --------- | -------
1|Ram|D1
2|Varun|D2
3|Ravi|D1
4|Amit|  ---
**Dept**

D_no | D_name | Address
----- | ----| --
D1|Hr|Hyd
D2|IT|Blr
D3|MRKT|Pune
```SELECT E_name from Emp NATURAL JOIN Dept ```
This command will return Ram, Varun.
* **Left (Outer) Join** :- It returns all record from the left table and also perform the Natural Join to return matched records from the right table.
```
	SELECT E_no, E_name, D_name, Address from Emp LEFT OUTER JOIN Dept ON(Emp.D_no = Dept.D_no)
```	
This command will return the following table:

E_no | E_name | D_name | Address
--|--|--|--
1|Ram|HR|Hyd
2|Varun|IT |Blr
3|Ravi|HR|Hyd
4|Amit| -- | --
* **Right (Outer) Join** :- It returns all records from right table, and the matched records from the left table.
```
	SELECT E_name, E_no, D_name, Address from Emp RIGHT OUTER JOIN Dept ON(Emp.D_no = Dept.D_no)
```
This command will return the following table.

E_no|E_name|D_name|Address
---|---|---|--
1|Ram|HR|Hyd
2|Varun|IT|Blr
3|Ravi|HR|Hyd
---|---|MRKT|Pune

-------------
## Aggregations in SQL
Aggregate Functions in SQL are :-
1. Sum( )
2. Avg( )
3. Min( )
4. Max( )
5. Count( )
-----
* Sum( ) :- Returns the sum of value that is specified. For e.g. ```SELECT SUM(marks) FROM Student```. This command will return sum of all the marks column in Student table.
* Avg( ) :- Returns the average value of a column that is specified. For e.g ```SELECT AVG(marks) FROM Student```
* Min( ) :- Returns the minimum value of a certain column. For e.g ```SELECT MIN(marks) FROM Student```.
* Max( ) :- Returns the maximum value of a certain column. For e.g. ```SELECT MAX(marks) FROM Student```.
* Count( ) :- Returns the count of number of rows. For e.g ```SELECT COUNT(*) FROM Student```. This will return count of all rows in Student table as (*) is used for all.
