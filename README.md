# LeetCode


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
<strong>My code result - Runtime: 544 ms, faster than 15.65% of Python3 online submissions for Longest Substring Without Repeating Characters. Memory Usage: 13.3 MB, less than 31.81% of Python3 online submissions for Longest Substring Without Repeating Characters.</strong>


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

<strong>My code result - Runtime: 88 ms, faster than 51.19% of Python3 online submissions for Add Two Numbers. Memory Usage: 13.2 MB, less than 74.42% of Python3 online submissions for Add Two Numbers.</strong>

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
