# LeetCode

## 6. ZigZag Conversion
### Medium

<a href='https://leetcode.com/problems/zigzag-conversion/'>https://leetcode.com/problems/zigzag-conversion/</a>

The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)
```
P   A   H   N
A P L S I I G
Y   I   R
```
And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:
```
string convert(string s, int numRows);
```
Example 1:
```
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```

Example 2:
```
Input: s = "PAYPALISHIRING", numRows = 4
Output: "PINALSIGYAHRPI"
Explanation:

P     I    N
A   L S  I G
Y A   H R
P     I
```
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 1032 ms, faster than 5.01% of Python3 online submissions for ZigZag Conversion.<br>
Memory Usage: 19.9 MB, less than 5.00% of Python3 online submissions for ZigZag Conversion.</strong>
<br>

```python
import math

class Solution:
    def convert(self, s: str, numRows: int) -> str:
        if (len(s) <= 1 or numRows <= 1):
            return s
        else:
            convmat = [[""] * math.ceil(len(s)/(2*numRows-2))*(numRows-1) for r in range(numRows)]

            ind = 0
            for i in range(math.ceil(len(s)/(2*numRows-2))):
                for j in range(2*numRows-2):
                    if (ind==len(s)):
                        break
                    else:
                        if (j < numRows):
                            convmat[j][i*(numRows-1)] = s[ind]
                            ind += 1
                        else:
                            convmat[2*numRows - j -2][j - numRows + 1 + i*(numRows-1)] = s[ind]
                            ind += 1
            res = ''
            for i in range(len(convmat)):
                for j in range(len(convmat[0])):
                    res += convmat[i][j]
            return res
```

<br><hr><br>



## 5. Longest Palindromic Substring
### Medium

<a href='https://leetcode.com/problems/longest-palindromic-substring/'>https://leetcode.com/problems/longest-palindromic-substring/</a>

Given a string s, find the longest palindromic substring in s. You may assume that the maximum length of s is 1000.

Example 1:
```
Input: "babad"
Output: "bab"
Note: "aba" is also a valid answer.
```

Example 2:
```
Input: "cbbd"
Output: "bb"
```
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 3660 ms, faster than 32.02% of Python3 online submissions for Longest Palindromic Substring.<br>
Memory Usage: 13.2 MB, less than 53.68% of Python3 online submissions for Longest Palindromic Substring.</strong>
<br>

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        result_len = 0
        result_str = ''
        whole_len = len(s)
        for i in range(whole_len):
            if whole_len - i < result_len:
                break
            else:
                for j in range(i+result_len+1, whole_len+1):
                    test_s = s[i:j]
                    if test_s == test_s[::-1]:
                        result_len = j - i
                        result_str = test_s
        return result_str
```

<br><hr><br>


## 3. Longest Substring Without Repeating Characters
### Medium

<a href='https://leetcode.com/problems/longest-substring-without-repeating-characters/'>https://leetcode.com/problems/longest-substring-without-repeating-characters/</a>

Given a string, find the length of the longest substring without repeating characters.

Example 1:
```
Input: "abcabcbb"
Output: 3 
Explanation: The answer is "abc", with the length of 3. 
```

Example 2:
```
Input: "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

Example 3:
```
Input: "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3. 
             Note that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 544 ms, faster than 15.65% of Python3 online submissions for Longest Substring Without Repeating Characters. <br>Memory Usage: 13.3 MB, less than 31.81% of Python3 online submissions for Longest Substring Without Repeating Characters.</strong>
<br>

```python
from collections import Counter
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        ln = len(s)
        if ln == 0:
            return 0
        else:
            res_ls = 0
            for i in range(0,ln):
                for j in range(res_ls,ln-i):
                    if max(Counter(s[i:i+j+1]).values())>1:
                        res_ls = max(res_ls,j)
                        break
                    elif j == ln-i-1:
                        res_ls = max(res_ls,j+1)
                        break
            return res_ls
```

<br><hr><br>

## 2. Add Two Numbers
### Medium

<a href='https://leetcode.com/problems/add-two-numbers/'>https://leetcode.com/problems/add-two-numbers/</a>

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example:
```
Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.
```

<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 88 ms, faster than 51.19% of Python3 online submissions for Add Two Numbers. <br>Memory Usage: 13.2 MB, less than 74.42% of Python3 online submissions for Add Two Numbers.</strong>
<br>

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        return self.convertNum2LN(self.convertLN2Num(l1) + self.convertLN2Num(l2))
           
            
    def convertLN2Num(self, l0: ListNode) -> int:
        res = l0.val
        i = 1
        while (l0.next != None):
            l0 = l0.next
            res = res + l0.val*10**i
            i += 1
        return res
    
    def convertNum2LN(self, num0: int) -> ListNode:
        if len(str(num0))==1:
            res = ListNode(num0)
            res.next = None
        else:
            res = ListNode(num0 % 10)
            res.next = self.convertNum2LN(num0 // 10)
        return res
```

<br><hr><br>
