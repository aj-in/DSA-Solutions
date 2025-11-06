Q1)  3110. Score of a String
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
        ascii_values = [ord(char) for char in my_string]
        print(ascii_values)
        summation = 0


        for i in range(0, len(my_string)):
            
            if i == len(my_string)-1:
                break
            summation = summation + abs (ascii_values[i] - ascii_values[i+1])  #used abs for Mathematical Mod function
            
        return summation
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
