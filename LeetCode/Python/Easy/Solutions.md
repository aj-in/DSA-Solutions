Q1)  
<br >
3110. Score of a String
<br>
You are given a string s. The score of a string is defined as the sum of the absolute difference between the ASCII values of adjacent characters.

Return the score of s.

 

Example 1:

Input: s = "hello"

Output: 13

Explanation:

The ASCII values of the characters in s are: 'h' = 104, 'e' = 101, 'l' = 108, 'o' = 111. So, the score of s would be |104 - 101| + |101 - 108| + |108 - 108| + |108 - 111| = 3 + 7 + 0 + 3 = 13.

Example 2:

Input: s = "zaz"

Output: 50

Explanation:

The ASCII values of the characters in s are: 'z' = 122, 'a' = 97. So, the score of s would be |122 - 97| + |97 - 122| = 25 + 25 = 50.

 

Constraints:

2 <= s.length <= 100
s consists only of lowercase English letters.

Link https://leetcode.com/problems/score-of-a-string/description/



Solution: 

```
class Solution:
    def scoreOfString(self, s: str) -> int:
        


        my_string = s
        ASCII_list = []

        for letter in my_string:
            ASCII_list.append(ord(letter))
        # print(ASCII_list)


        ASCII_sum=0


        for i in range(0,len(my_string)):
            
            if i == len(my_string)-1:
                break
            
            ASCII_sum = ASCII_sum + abs( ASCII_list[i]  - ASCII_list [i+1] )
            
        return(ASCII_sum)


```
<br>
<br>


Notes: Index goes out of range for the last iteraion naturally as we still try to increment even if we dont have item to increment
Handle that edge case with 'if' block



<br>
<br>



Q2)  
<br>

2894. Divisible and Non-divisible Sums Difference
<br>
2894. Divisible and Non-divisible Sums Difference
Solved
Easy
Topics
premium lock icon
Companies
Hint
You are given positive integers n and m.

Define two integers as follows:

num1: The sum of all integers in the range [1, n] (both inclusive) that are not divisible by m.
num2: The sum of all integers in the range [1, n] (both inclusive) that are divisible by m.
Return the integer num1 - num2.


Link https://leetcode.com/problems/divisible-and-non-divisible-sums-difference/description/


Solution: 

```
class Solution:
    def differenceOfSums(self, n: int, m: int) -> int:


        num1 = num2 = 0                  #unpacking 

        for i in range(1,n+1):
            
            
            # num1
            if i%m!=0:
                num1 = num1 + i
            
            # num2
            else:
                num2=num2+i
            
        return(num1-num2)
```
<br>
<br>


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
