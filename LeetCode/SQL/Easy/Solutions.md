

Q1)  175. Combine Two Tables


<br>
Table: Person

+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| personId    | int     |
| lastName    | varchar |
| firstName   | varchar |
+-------------+---------+
personId is the primary key (column with unique values) for this table.
This table contains information about the ID of some persons and their first and last names.
 

Table: Address

+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| addressId   | int     |
| personId    | int     |
| city        | varchar |
| state       | varchar |
+-------------+---------+
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
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| email       | varchar |
+-------------+---------+
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
