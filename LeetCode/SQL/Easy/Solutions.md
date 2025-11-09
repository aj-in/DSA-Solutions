

Q1)  175. Combine Two Tables


<br>
Table: Person

```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| personId    | int     |
| lastName    | varchar |
| firstName   | varchar |
+-------------+---------+

```
personId is the primary key (column with unique values) for this table.
This table contains information about the ID of some persons and their first and last names.
 

Table: Address
```

+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| addressId   | int     |
| personId    | int     |
| city        | varchar |
| state       | varchar |
+-------------+---------+
```
addressId is the primary key (column with unique values) for this table.
Each row of this table contains information about the city and state of one person with ID = PersonId.
 

Write a solution to report the first name, last name, city, and state of each person in the Person table. If the address of a personId is not present in the Address table, report null instead.

Link [https://www.hackerrank.com/challenges/average-population-of-each-continent/problem?isFullScreen=true](https://leetcode.com/problems/combine-two-tables/description/)


Solution: 

```
select P.firstName, P.lastName, A.city, A.state
from Person as P
left join
Address as A
on
P.personID = A.personID;

```
<br>
<br>



Q2) 182. Duplicate Emails


<br>



```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| email       | varchar |
+-------------+---------+
```
id is the primary key (column with unique values) for this table.
Each row of this table contains an email. The emails will not contain uppercase letters.
 

Write a solution to report all the duplicate emails. Note that it's guaranteed that the email field is not NULL.

Return the result table in any order.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
with dup_count as (select email, count(*) from Person
group by email 
having count(*)> 1)

Select email from dup_count;
```
<br>
<br>

Logic: use a group by to group on the count of unique mails


Q3)  183. Customers Who Never Order



<br>
Table: Customers

+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| name        | varchar |
+-------------+---------+
id is the primary key (column with unique values) for this table.
Each row of this table indicates the ID and name of a customer.
 

Table: Orders

+-------------+------+
| Column Name | Type |
+-------------+------+
| id          | int  |
| customerId  | int  |
+-------------+------+
id is the primary key (column with unique values) for this table.
customerId is a foreign key (reference columns) of the ID from the Customers table.
Each row of this table indicates the ID of an order and the ID of the customer who ordered it.
 

Write a solution to find all customers who never order anything.

Return the result table in any order.




Link [https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true](https://leetcode.com/problems/customers-who-never-order/description/)


Solution: 

```
select c.name as Customers from customers as c
left join orders as o
on 
c.id = o.customerId
where o.customerID is null;
```
<br>
<br>

Logic......

Considered an inner join, but that would only give me the customers who made a purchase (So made a purchase joins with customers table NO USE)
<br>
BUT
with 
Left join I can get null where nobody made an order to detect based on the NULL values, I thought of using left or right join

in left join placed customers on left, so i see where null pops up because htey wont have made an order  



Q4)  511. Game Play Analysis I ***

<br>

Link [https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true
](https://leetcode.com/problems/game-play-analysis-i/)

Solution: 

```
select player_id, min(event_date) as first_login
from Activity
group by player_id 
```
<br>
<br>

Logic: 
<Br>


Why GROUP BY Before MIN()?

<br>
GROUP BY player_id organizes the table into groups where each group contains all rows for a specific player_id.<br>

After the rows are grouped, MIN(event_date) finds the earliest event_date within each group.<br>

If MIN() were applied first (without grouping), it would find the single earliest date across the entire table, regardless of player_id. <br>
This would give you only one row (the earliest login of any player), which isn’t what you want.

<br>
<br>


Q5)  
1068. Product Sales Analysis I
<br>
Table: Sales

+-------------+-------+
| Column Name | Type  |
+-------------+-------+
| sale_id     | int   |
| product_id  | int   |
| year        | int   |
| quantity    | int   |
| price       | int   |
+-------------+-------+
(sale_id, year) is the primary key (combination of columns with unique values) of this table.
product_id is a foreign key (reference column) to Product table.
Each row of this table shows a sale on the product product_id in a certain year.
Note that the price is per unit.
 

Table: Product

+--------------+---------+
| Column Name  | Type    |
+--------------+---------+
| product_id   | int     |
| product_name | varchar |
+--------------+---------+
product_id is the primary key (column with unique values) of this table.
Each row of this table indicates the product name of each product.
 

Write a solution to report the product_name, year, and price for each sale_id in the Sales table.

Return the resulting table in any order.



Link https://leetcode.com/problems/product-sales-analysis-i/description/

Solution: 

```
select p.product_name, s.year, s.price from Sales as s
join 
Product as p
on
s.product_id = p.product_id;
```
<br>
<br>





Q6) 
1378. Replace Employee ID With The Unique Identifier
<br>
+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| name          | varchar |
+---------------+---------+
id is the primary key (column with unique values) for this table.
Each row of this table contains the id and the name of an employee in a company.
 

Table: EmployeeUNI

+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| unique_id     | int     |
+---------------+---------+
(id, unique_id) is the primary key (combination of columns with unique values) for this table.
Each row of this table contains the id and the corresponding unique id of an employee in the company.
 

Write a solution to show the unique ID of each user, If a user does not have a unique ID replace just show null.

Return the result table in any order.

The result format is in the following example.

Link https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/description/

Solution: 

```
select u.unique_id, e.name from Employees as e
left join              -- left join because they didnt want to prioritize one of the tables, they wanted NULL for absesnce which left or right join does
EmployeeUNI as u 
on
e.id = u.id  
```
<br>
<br>





Q7)  
1407. Top Travellers
<br>
```
+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| name          | varchar |
+---------------+---------+
```
id is the column with unique values for this table.
name is the name of the user.
 

Table: Rides
```
+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| user_id       | int     |
| distance      | int     |
+---------------+---------+
```
id is the column with unique values for this table.
user_id is the id of the user who traveled the distance "distance".
 

Write a solution to report the distance traveled by each user.

Return the result table ordered by travelled_distance in descending order, if two or more users traveled the same distance, order them by their name in ascending order.

The result format is in the following example.

 

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
select u.name,   IFNULL(sum(r.distance), 0) as 'travelled_distance'  from 
Users as u
left join
Rides as r
on 
u.id = r.user_id
group by u.id

order by 2 desc, 1 asc;
```
<br>
<br>


Notes: Use IFNULL(column_name, replacement) **** to deal with null values, also check before JOINING how to deal with NULLs and no matchec if nothign then inner join if we want NULLS then left/right


<br>
<br>

Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>




Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>




Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>





Q1)  Revising the Select Query I
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true


Solution: 

```
Select * from CITY
where POPULATION> 100000 and
COUNTRYCODE = 'USA';
```
<br>
<br>


