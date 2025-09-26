

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
