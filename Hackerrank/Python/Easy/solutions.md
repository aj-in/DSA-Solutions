Q1)  Say "Hello, World!" With Python
<br>
The above code will print Hello, World! on your screen. Try it yourself in the editor below!

Link [https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true](https://www.hackerrank.com/challenges/py-hello-world/problem?isFullScreen=true)


Solution: 

```
print("Hello, World!")
```
<br>
<br>


Q2)  Python If-Else
<br>
Given an integer, , perform the following conditional actions:

If  is odd, print Weird
If  is even and in the inclusive range of  to , print Not Weird
If  is even and in the inclusive range of  to , print Weird
If  is even and greater than , print Not Weird

Link [https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true
](https://www.hackerrank.com/challenges/py-if-else/problem?isFullScreen=true)

Solution: 

```

if n%2!=0:
    print("Weird")
    
elif n%2==0 and 2 <= n  <= 5:
    print("Not Weird")
    
    
elif n%2==0 and 6 <= n  <= 20:
    print("Weird")
    
elif n%2==0 and n>20:
    print("Not Weird")
```
<br>
<br>


Q3)  Arithmetic Operators
<br>
Task
The provided code stub reads two integers from STDIN,  and . Add code to print three lines where:

The first line contains the sum of the two numbers.
The second line contains the difference of the two numbers (first - second).
The third line contains the product of the two numbers.

Link [https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true](https://www.hackerrank.com/challenges/python-arithmetic-operators/problem?isFullScreen=true)


Solution: 

```
print(a+b)
print(a-b)
print(a*b)
```
<br>
<br>


Q3) Python: Division
<br>
The provided code stub reads two integers,  and , from STDIN.

Add logic to print two lines. The first line should contain the result of integer division,  // . The second line should contain the result of float division,  / .

No rounding or formatting is necessary.

Example


The result of the integer division .
The result of the float division is .

Link hackerrank.com/challenges/python-division?isFullScreen=true

Solution: 

```
print(a//b)
print(a/b)
```
<br>
<br>


Q4)  Loops
<br>
Task
The provided code stub reads an integer, , from STDIN. For all non-negative integers , print .

Example

The list of non-negative integers that are less than  is . Print the square of each number on a separate line.
Link [https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true](https://www.hackerrank.com/challenges/python-loops/problem?isFullScreen=true)


Solution: 

```
for i in range (0, n):
    print(i ** 2)
```
<br>
<br>


Q5) Print Function
<br>
Check Tutorial tab to know how to to solve.

The included code stub will read an integer, , from STDIN.

Without using any string methods, try to print the following:


Note that "" represents the consecutive values in between.

Example

Print the string .

Input Format

The first line contains an integer .

Link [https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true
](https://www.hackerrank.com/challenges/python-print/problem?isFullScreen=true)

Solution: 

```
for i in range(1,n+1):                         //dont forget the +1 end of range in exclusive
    print(i, end='')
```
<br>
<br>


Q6)  Find the Runner-Up Score!
<br>
Given the participants' score sheet for your University Sports Day, you are required to find the runner-up score. You are given  scores. Store them in a list and find the score of the runner-up.

Input Format

The first line contains . The second line contains an array   of  integers each separated by a space.

Constraints

Output Format

Print the runner-up score.

Sample Input 0

5
2 3 6 6 5
Sample Output 0

5
Explanation 0

Given list is . The maximum score is , second maximum is . Hence, we print  as the runner-up score.



Link [[https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true](https://www.hackerrank.com/challenges/find-second-maximum-number-in-a-list/problem?isFullScreen=true)](https://www.hackerrank.com/challenges/find-second-maximum-number-in-a-list/problem?isFullScreen=true)


Solution: 

```
if __name__ == '__main__':
    n = int(input())
    arr = list(map(int, input().split()))          //Tampered with thee question kinda

arr.sort()


max_val = max(arr)

while max_val in arr:
    arr.remove(max_val)
    
    
print(max(arr))


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
