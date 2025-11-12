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


Q3)  

1920. Build Array from Permutation
<br>
Given a zero-based permutation nums (0-indexed), build an array ans of the same length where ans[i] = nums[nums[i]] for each 0 <= i < nums.length and return it.

A zero-based permutation nums is an array of distinct integers from 0 to nums.length - 1 (inclusive).

 

Example 1:

Input: nums = [0,2,1,5,3,4]
Output: [0,1,2,4,5,3]
Explanation: The array ans is built as follows: 
ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
    = [nums[0], nums[2], nums[1], nums[5], nums[3], nums[4]]
    = [0,1,2,4,5,3]
Example 2:

Input: nums = [5,0,1,2,3,4]
Output: [4,5,0,1,2,3]
Explanation: The array ans is built as follows:
ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
    = [nums[5], nums[0], nums[1], nums[2], nums[3], nums[4]]
    = [4,5,0,1,2,3]
 

Constraints:

1 <= nums.length <= 1000
0 <= nums[i] < nums.length
The elements in nums are distinct.
 

Follow-up: Can you solve it without using an extra space (i.e., O(1) memory)?
Link https://leetcode.com/problems/build-array-from-permutation/

Solution: 

```
class Solution:
    def buildArray(self, nums: List[int]) -> List[int]:
        ans =[]
        for i in range(0, len(nums)):
            ans.append(nums[nums[i]])
            
        return(ans)
```
<br>
<br>



Q4) 
1929. Concatenation of Array
<br>
Given an integer array nums of length n, you want to create an array ans of length 2n where ans[i] == nums[i] and ans[i + n] == nums[i] for 0 <= i < n (0-indexed).

Specifically, ans is the concatenation of two nums arrays.

Return the array ans.

Link: https://leetcode.com/problems/concatenation-of-array/description/
 

Example 1:

Input: nums = [1,2,1]
Output: [1,2,1,1,2,1]
Explanation: The array ans is formed as follows:
- ans = [nums[0],nums[1],nums[2],nums[0],nums[1],nums[2]]
- ans = [1,2,1,1,2,1]
Example 2:

Input: nums = [1,3,2,1]
Output: [1,3,2,1,1,3,2,1]
Explanation: The array ans is formed as follows:
- ans = [nums[0],nums[1],nums[2],nums[3],nums[0],nums[1],nums[2],nums[3]]
- ans = [1,3,2,1,1,3,2,1]
 

Constraints:

n == nums.length
1 <= n <= 1000
1 <= nums[i] <= 1000

Solution: 

```
class Solution:
    def getConcatenation(self, nums: List[int]) -> List[int]:
        ans = []
        for i in nums:

            ans.append(i)
        
        for i in nums:

            ans.append(i)
        return ans
```
<br>
<br>




Q5) 
2011. Final Value of Variable After Performing Operations
<br>
There is a programming language with only four operations and one variable X:

++X and X++ increments the value of the variable X by 1.
--X and X-- decrements the value of the variable X by 1.
Initially, the value of X is 0.

Given an array of strings operations containing a list of operations, return the final value of X after performing all the operations.

 

Example 1:

Input: operations = ["--X","X++","X++"]
Output: 1
Explanation: The operations are performed as follows:
Initially, X = 0.
--X: X is decremented by 1, X =  0 - 1 = -1.
X++: X is incremented by 1, X = -1 + 1 =  0.
X++: X is incremented by 1, X =  0 + 1 =  1.
Example 2:

Input: operations = ["++X","++X","X++"]
Output: 3
Explanation: The operations are performed as follows:
Initially, X = 0.
++X: X is incremented by 1, X = 0 + 1 = 1.
++X: X is incremented by 1, X = 1 + 1 = 2.
X++: X is incremented by 1, X = 2 + 1 = 3.
Example 3:

Input: operations = ["X++","++X","--X","X--"]
Output: 0
Explanation: The operations are performed as follows:
Initially, X = 0.
X++: X is incremented by 1, X = 0 + 1 = 1.
++X: X is incremented by 1, X = 1 + 1 = 2.
--X: X is decremented by 1, X = 2 - 1 = 1.
X--: X is decremented by 1, X = 1 - 1 = 0.
 

Constraints:

1 <= operations.length <= 100
operations[i] will be either "++X", "X++", "--X", or "X--".

Link: https://leetcode.com/problems/final-value-of-variable-after-performing-operations/description/

Solution: 

```
class Solution:
    def finalValueAfterOperations(self, operations: List[str]) -> int:
        X=0
        for i in operations:
            
            if i == "--X" or i == "X--":
                X= X-1

            elif i == "++X" or i == "X++":
                X= X+1

        return X

```
<br>
<br>
Notes: 

```
Brute forece-convert the strings into conditional statements 
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
