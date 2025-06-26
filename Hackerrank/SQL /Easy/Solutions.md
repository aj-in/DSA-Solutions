


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

Q2) Revising the Select Query II
<br>
Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

Link https://www.hackerrank.com/challenges/revising-the-select-query-2/problem?isFullScreen=true


Solution: 

```
Select Name from City
where population > 120000
and CountryCode ='USA';
```
<br>
<br>

Q3) Select All
<br>
Query all columns (attributes) for every row in the CITY table.

Link https://www.hackerrank.com/challenges/select-all-sql/problem?isFullScreen=true

```
select * from City;
```

<br>
<br>







Q4) Select By ID
<br>
Query all columns for a city in CITY with the ID 1661.

Link [https://www.hackerrank.com/challenges/select-all-sql/problem?isFullScreen=true](https://www.hackerrank.com/challenges/select-by-id/problem?isFullScreen=true)



```
Select * from City
where ID = 1661;
```

<br>
<br>


Q5) Japanese Cities' Attributes
<br>
Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.


Link https://www.hackerrank.com/challenges/japanese-cities-attributes/problem?isFullScreen=true


```
select * from city
where COUNTRYCODE ='JPN';

```

<br>
<br>



Q6) Japanese Cities' Names

<br>
Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
Link https://www.hackerrank.com/challenges/japanese-cities-name/problem?isFullScreen=true



```
select name from city
where COUNTRYCODE ='JPN';
```

<br>
<br>






