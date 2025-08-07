


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

Notes: Just fetched the name column
<br>
<br>


Q7) Weather Observation Station 1



<br>

Query a list of CITY and STATE from the STATION table.

Link https://www.hackerrank.com/challenges/weather-observation-station-1/problem?isFullScreen=true



```
select CITY, STATE
from STATION ;
```

<br>
<br>


Q8)  Weather Observation Station 3
<br>
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
Link https://www.hackerrank.com/challenges/weather-observation-station-3/problem?isFullScreen=true


```
select distinct(CITY) from STATION 
where ID%2=0;
```

<br>
Note: Any even division leaves no fractions i.e. they are evenly divided, leaving no carry overs/remainders, if there are any then its odd
so we evenly divide ...x%2 and check if the value is 0 or not.


<br>
<br>



Q9) Weather Observation Station 4

<br>

Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

Link https://www.hackerrank.com/challenges/weather-observation-station-4/problem?isFullScreen=true




```
select count(CITY) - count(distinct(CITY))   //maybe helpful in finding duplicatess
from station;
```

<br>
<br>


<br>







Q10) Weather Observation Station 5 ***



<br>

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
<br>

Sample Input

For example, CITY has four entries: DEF, ABC, PQRS and WXY.

Sample Output

ABC 3
PQRS 4
Explanation

When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths  and . The longest name is PQRS, but there are  options for shortest named city. Choose ABC, because it comes first alphabetically.

Note
You can write two separate queries to get the desired output. It need not be a single query.

Link https://www.hackerrank.com/challenges/weather-observation-station-5/problem?isFullScreen=true



```
select city, length(city) as CityLength
from station
order by CityLength desc, city asc
limit 1;


select city, length(city) as CityLength
from station
order by CityLength asc, city asc
limit 1;

```

<br>

select city, min(length(city)) <br>
from station <br>
order by city  // This is wrong logic 1/2 of the output is to aggregated ,but the other half isnt


<br>
<br>

after everything we need an overarching min so we can aggreagate over teh non aagreagating function i.e the ones that keeps number of rows constant....



<br>
<br>





Q11) Weather Observation Station 6

<br>

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

Link https://www.hackerrank.com/challenges/weather-observation-station-6/problem?isFullScreen=true



select distinct(city) from station
where city like '%a'
or
where city like '%e'
or
where city like '%i'
or
where city like '%o'
or
where city like '%u';


the above approach is syntactically wrong

instead 



```
select distinct(city) from station
where city like 'a%'             
or
 city like 'e%'
or
 city like 'i%'
or
 city like 'o%'
or
 city like 'u%'; 
```




<br>


or use regexp (Regular Expressions)

select distinct(city)
from station
where city like regexp '^[a,e,i,o,u]';      .... no need of commas and a like 


```
select distinct(city)
from station
where city regexp '^[aeiou]';
```

<br>
<br>


<br>


Q12) Weather Observation Station 7



<br>

Query the list of CITY names **ending** with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Link https://www.hackerrank.com/challenges/weather-observation-station-7/problem?isFullScreen=true



```
select distinct(city)
from station

where city regexp '[aeiou]$';
```

<br>

Regexp starts with ^ and ends with $
<br>

<br>


Q13) Weather Observation Station 8
<br>
Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Link https://www.hackerrank.com/challenges/weather-observation-station-8/problem?isFullScreen=true

```
select distinct(City)

from station


where city regexp '^[aeiou]'


and city regexp '[aeiou]$';
```

<br>

Note 
where city regexp '^[aeiou].[aeiou]$';  // this wont work we need 

where city regexp '^[aeiou].*[aeiou]$';  // this matches all characters  


<br>
<br>


Q14) Weather Observation Station 9

<br>
Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Link https://www.hackerrank.com/challenges/weather-observation-station-9/problem?isFullScreen=true



```
select distinct(city)
from station

where city not regexp '^[aeiou]';
```

<br>

<br>


Q15) Weather Observation Station 10

<br>

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.


Link https://www.hackerrank.com/challenges/weather-observation-station-10/problem?isFullScreen=true



```
select distinct(city)
from station

where city not regexp '[aeiou]$';


```

<br>

<br>
<br>

Q16) Weather Observation Station 11
<br>
Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Link  https://www.hackerrank.com/challenges/weather-observation-station-11/problem?isFullScreen=true


Solution: 

```
select distinct city
from station 
where city not regexp '^[aeiou]'
or 
city not regexp '[aeiou]$';

```
<br>
Note: pay attention to AND or OR ...read question carefully 
<br>
<br>

Q17) Weather Observation Station 12
<br>
Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.
Link https://www.hackerrank.com/challenges/weather-observation-station-12/problem?isFullScreen=true


Solution: 

```
select distinct city
from station 
where city not regexp '^[aeiou]'
and 
city not regexp '[aeiou]$';

```
<br>

<br>

Q18) Higher Than 75 Marks
<br>
Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Link https://www.hackerrank.com/challenges/more-than-75-marks/problem?isFullScreen=true


Solution: 

```
SELECT Name
FROM students
WHERE Marks > 75
ORDER BY right(Name, 3), ID ASC; 
```
<br>
Note: you can split string with right(col name, 3)  ....3 is for 3 chracters from right in this case
<br>
<br>


Q19) Employee Names
<br>
Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.
Link https://www.hackerrank.com/challenges/name-of-employees/problem?isFullScreen=true


Solution: 

```
select name from employee
order by name; 
```
<br>

<br>


Q20) Employee Salaries
<br>
Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than 2000$ per month who have been employees for less than  months. Sort your result by ascending employee_id.

Link https://www.hackerrank.com/challenges/more-than-75-marks/problem?isFullScreen=true


Solution: 

```
select name from employee
where salary > 2000 and months <10
order by employee_id;
```
<br>
<br>


Q22)  Revising Aggregations - The Count Function
<br>
Query a count of the number of cities in CITY having a Population larger than 100000.

Link https://www.hackerrank.com/challenges/revising-aggregations-the-count-function/problem?isFullScreen=true


Solution: 

```
select count(*)
from City
where population> 100000;
```
<br>
<br>

Q23) Revising Aggregations - The Sum Function

<br>
Query the total population of all cities in CITY where District is California.

Link: https://www.hackerrank.com/challenges/revising-aggregations-sum/problem?isFullScreen=true

Solution:

```

select sum(population) from CITY 
where District = 'California';

```


