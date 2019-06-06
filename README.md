# LeetCode

Runtime Statistics:<br>
Top 0-20%   : 3 times   <br>
Top 20-40%  : 2 time    <br>
Top 40-60%  : 3 times    <br>
Top 60-80%  : 0 time    <br>
Top 80-100% : 7 times   <br>


Hyperlink<br>
[2. Add Two Numbers (Medium)](https://github.com/daydreamersjp/LeetCode#2-add-two-numbers)
[3. Longest Substring Without Repeating Characters (Medium)](https://github.com/daydreamersjp/LeetCode#3-longest-substring-without-repeating-characters)
[5. Longest Palindromic Substring (Medium)](https://github.com/daydreamersjp/LeetCode#5-longest-palindromic-substring)
[6. ZigZag Conversion (Medium)](https://github.com/daydreamersjp/LeetCode#6-zigzag-conversion)
[7. Reverse Integer (Easy)](https://github.com/daydreamersjp/LeetCode#7-reverse-integer)
[8. String to Integer (atoi) (Medium)](https://github.com/daydreamersjp/LeetCode#8-string-to-integer-atoi)
[9. Palindrome Number (Easy)](https://github.com/daydreamersjp/LeetCode#9-palindrome-number)
[11. Container With Most Water (Medium)](https://github.com/daydreamersjp/LeetCode#11-container-with-most-water)
[12. Integer to Roman (Medium)](https://github.com/daydreamersjp/LeetCode#12-integer-to-roman)
[13. Roman to Integer (Easy)](https://github.com/daydreamersjp/LeetCode#13-roman-to-integer)
[14. Longest Common Prefix (Easy)](https://github.com/daydreamersjp/LeetCode#14-longest-common-prefix)
[16. 3Sum Closest (Medium)](https://github.com/daydreamersjp/LeetCode#16-3sum-closest)
[17. Letter Combinations of a Phone Number (Medium)](https://github.com/daydreamersjp/LeetCode#17-letter-combinations-of-a-phone-number)
[18. 4Sum (Medium)](https://github.com/daydreamersjp/LeetCode#18-4sum)
[20. Valid Parentheses (Easy)](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#20-valid-parentheses)



<hr>

## 20. Valid Parentheses
### Easy

<a href='https://leetcode.com/problems/valid-parentheses/'>https://leetcode.com/problems/valid-parentheses/</a>

Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Note that an empty string is also considered valid.

Example 1:
```
Input: "()"
Output: true
```
Example 2:
```
Input: "()[]{}"
Output: true
```
Example 3:
```
Input: "(]"
Output: false
```
Example 4:
```
Input: "([)]"
Output: false
```
Example 5:
```
Input: "{[]}"
Output: true
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 44 ms, faster than 27.52% of Python3 online submissions for Valid Parentheses.<br>
Memory Usage: 13.2 MB, less than 42.31% of Python3 online submissions for Valid Parentheses.</strong>
<br>

```python
class Solution:
    def isValid(self, s: str) -> bool:
        if (s==''): return True
        
        s0 = ''
        s1 = s
        while (s0!=s1):
            s0 = s1
            s1 = s1.replace('()','').replace('{}','').replace('[]','')
        if (s1==''): return True
        else: return False
```

<br><hr><br>

## 18. 4Sum
### Medium

<a href='https://leetcode.com/problems/4sum/'>https://leetcode.com/problems/4sum/</a>

Given an array nums of n integers and an integer target, are there elements a, b, c, and d in nums such that a + b + c + d = target? Find all unique quadruplets in the array which gives the sum of target.

Note:

The solution set must not contain duplicate quadruplets.

Example:
```
Given array nums = [1, 0, -1, 0, -2, 2], and target = 0.

A solution set is:
[
  [-1,  0, 0, 1],
  [-2, -1, 1, 2],
  [-2,  0, 0, 2]
]
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 2176 ms, faster than 5.00% of Python3 online submissions for 4Sum.<br>
Memory Usage: 13.2 MB, less than 69.46% of Python3 online submissions for 4Sum.</strong>
<br>

```python
class Solution:
    def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
        if (len(nums)<=3): return []
        if (len(nums)==4 and sum(nums)==target): return [nums]
        
        nums.sort()
        
        res = []
        
        for a in range(len(nums)-3):
            for b in range(a+1,len(nums)-2):
                if (b<a+1 and nums[b-1]==nums[b]): 
                    continue
                    
                c = b+1
                d = len(nums)-1
                
                while (c!=d):
                    if (nums[a]+nums[b]+nums[c]+nums[d]==target):
                        res_t = [nums[a],nums[b],nums[c],nums[d]]
                        if res_t not in res:
                            res += [res_t]
                        if (d-c==1): 
                            break
                        else:
                            c += 1
                            d -= 1
                    elif (nums[a]+nums[b]+nums[c]+nums[d]>target):
                        d -= 1
                    elif (nums[a]+nums[b]+nums[c]+nums[d]<target):
                        c += 1
        
        
        
        return res
```

<br><hr><br>

## 17. Letter Combinations of a Phone Number
### Medium

<a href='https://leetcode.com/problems/letter-combinations-of-a-phone-number/'>https://leetcode.com/problems/letter-combinations-of-a-phone-number/</a>

Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent.

A mapping of digit to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.

img[](./img/200px-Telephone-keypad2.svg.png)

Example:
```
Input: "23"
Output: ["ad", "ae", "af", "bd", "be", "bf", "cd", "ce", "cf"].
```
Note:

Although the above answer is in lexicographical order, your answer could be in any order you want.

<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 28 ms, faster than 99.42% of Python3 online submissions for Letter Combinations of a Phone Number.<br>
Memory Usage: 13 MB, less than 87.66% of Python3 online submissions for Letter Combinations of a Phone Number.</strong>
<br>

```python
import itertools

class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        if (len(digits)==0): return []
        
        dc = {
            '2': ['a','b','c'],
            '3': ['d','e','f'],
            '4': ['g','h','i'],
            '5': ['j','k','l'],
            '6': ['m','n','o'],
            '7': ['p','q','r','s'],
            '8': ['t','u','v'],
            '9': ['w','x','y','z'],
        }
        
        strlis = [dc[d] for d in digits]
        
        resls = [list(comb) for comb in itertools.product(*strlis)]
        
        
        
        res = []
        for i in range(len(resls)):
            res_t = ''
            for j in range(len(resls[i])):
                res_t += resls[i][j]
            res += [res_t]
        
        return res
            
```

<br><hr><br>

## 16. 3Sum Closest
### Medium

<a href='https://leetcode.com/problems/3sum-closest/'>https://leetcode.com/problems/3sum-closest/</a>

Given an array nums of n integers and an integer target, find three integers in nums such that the sum is closest to target. Return the sum of the three integers. You may assume that each input would have exactly one solution.

Example:
```
Given array nums = [-1, 2, 1, -4], and target = 1.

The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).
```
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 92 ms, faster than 90.68% of Python3 online submissions for 3Sum Closest.<br>
Memory Usage: 13.2 MB, less than 46.15% of Python3 online submissions for 3Sum Closest.</strong>
<br>

```python
class Solution:
    def threeSumClosest(self, nums: List[int], target: int) -> int:
        nums.sort()
        
        res = nums[0] + nums[1] + nums[2]
        
        for x in range(0,len(nums)-2):
            if x > 0 and nums[x] == nums[x - 1]:
                continue
                
            y=x+1
            z=len(nums)-1
            
            while (y!=z):
                total = nums[x]+nums[y]+nums[z]
                if (abs(total-target)<abs(res-target)):
                    res = total
                    
                if (total>target):
                    z -= 1
                elif (total<target):
                    y += 1
                else:
                    return res
        
        return res
```

<br><hr><br>

## 14. Longest Common Prefix
### Easy

<a href='https://leetcode.com/problems/longest-common-prefix/'>https://leetcode.com/problems/longest-common-prefix/</a>

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

Example 1:
```
Input: ["flower","flow","flight"]
Output: "fl"
```

Example 2:
```
Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```
Note:

All given inputs are in lowercase letters a-z.
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 36 ms, faster than 92.77% of Python3 online submissions for Longest Common Prefix.<br>
Memory Usage: 13.2 MB, less than 55.78% of Python3 online submissions for Longest Common Prefix.</strong>
<br>

```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if len(strs)==0: return ''
        if len(strs)==1: return strs[0]
        
        res = ''
        
        strsset = set(strs)
        strsset = sorted(strsset,key=len)
        
        i = 0
        res = ''
        common = True
        while (i < len(strsset[0]) and common == True):
            for j in range(1,len(strsset)):
                if strsset[0][i] != strsset[j][i]:
                    common = False
                    break
            if (common == True):
                res += strsset[0][i]
            i += 1
        
        return res
```

<br><hr><br>

## 13. Roman to Integer
### Easy

<a href='https://leetcode.com/problems/roman-to-integer/'>https://leetcode.com/problems/roman-to-integer/</a>

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```
For example, two is written as II in Roman numeral, just two one's added together. Twelve is written as, XII, which is simply X + II. The number twenty seven is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9. 
X can be placed before L (50) and C (100) to make 40 and 90. 
C can be placed before D (500) and M (1000) to make 400 and 900.
Given a roman numeral, convert it to an integer. Input is guaranteed to be within the range from 1 to 3999.

Example 1:
```
Input: "III"
Output: 3
```
Example 2:
```
Input: "IV"
Output: 4
```
Example 3:
```
Input: "IX"
Output: 9
```
Example 4:
```
Input: "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.
```
Example 5:
```
Input: "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 56 ms, faster than 95.07% of Python3 online submissions for Roman to Integer.
<br>Memory Usage: 13.1 MB, less than 97.82% of Python3 online submissions for Roman to Integer.</strong>
<br>

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        twoChar = {'IV': 4,
                   'IX': 9,
                   'XL': 40,
                   'XC': 90,
                   'CD': 400,
                   'CM': 900,}
        oneChar = {'I': 1,
                   'V': 5,
                   'X': 10,
                   'L': 50,
                   'C': 100,
                   'D': 500,
                   'M': 1000,}
        
        s_t = s
        res = 0
        while (len(s_t) != 0):
            if (s_t[0:2] in twoChar): 
                res += twoChar[s_t[0:2]]
                s_t = s_t[2:]
            else: 
                res += oneChar[s_t[0]]
                s_t = s_t[1:]
        
        return res
```

<br><hr><br>

## 12. Integer to Roman
### Medium

<a href='https://leetcode.com/problems/integer-to-roman/'>https://leetcode.com/problems/integer-to-roman/</a>

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```
For example, two is written as II in Roman numeral, just two one's added together. Twelve is written as, XII, which is simply X + II. The number twenty seven is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9. 
X can be placed before L (50) and C (100) to make 40 and 90. 
C can be placed before D (500) and M (1000) to make 400 and 900.
Given an integer, convert it to a roman numeral. Input is guaranteed to be within the range from 1 to 3999.

Example 1:
```
Input: 3
Output: "III"
```
Example 2:
```
Input: 4
Output: "IV"
```
Example 3:
```
Input: 9
Output: "IX"
```
Example 4:
```
Input: 58
Output: "LVIII"
Explanation: L = 50, V = 5, III = 3.
```
Example 5:
```
Input: 1994
Output: "MCMXCIV"
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 68 ms, faster than 54.02% of Python3 online submissions for Integer to Roman.<br>
Memory Usage: 13.3 MB, less than 68.40% of Python3 online submissions for Integer to Roman.</strong>
<br>

```python
class Solution:
    def intToRoman(self, num: int) -> str:
        thousand = hundred = ten = one = 0        
        
        thousand = num // 1000
        hundred = (num // 100) - thousand * 10
        ten = (num // 10) - thousand * 100 - hundred *10
        one = num % 10
       
        return self.Roman0to9byPos(thousand,'M','_','_') + \
               self.Roman0to9byPos(hundred,'C','D','M') + \
               self.Roman0to9byPos(ten,'X','L','C') + \
               self.Roman0to9byPos(one,'I','V','X')        

    
    def Roman0to9byPos(self,num,one,five,ten):
        'expect num: 0-9'
        'others: str'
        if (num==0): return ''
        elif (num<=3): return one*num
        elif (num==4): return one+five
        elif (num==5): return five
        elif (num<=8): return five+one*(num-5)
        else: return one+ten
```

<br><hr><br>

## 11. Container With Most Water
### Medium

<a href='https://leetcode.com/problems/container-with-most-water/'>https://leetcode.com/problems/container-with-most-water/</a>

Given n non-negative integers a_1, a_2, ..., a_n , where each represents a point at coordinate (i, a_i). n vertical lines are drawn such that the two endpoints of line i is at (i, a_i) and (i, 0). Find two lines, which together with x-axis forms a container, such that the container contains the most water.

Note: You may not slant the container and n is at least 2.

![](./img/question_11.jpg)

The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.

 

Example:
```
Input: [1,8,6,2,5,4,8,3,7]
Output: 49
```
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 68 ms, faster than 58.56% of Python3 online submissions for Container With Most Water.
<br>Memory Usage: 14.5 MB, less than 43.08% of Python3 online submissions for Container With Most Water.</strong>
<br>

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        
        le_ind = 0
        re_ind = len(height) - 1
        vol = min(height[le_ind], height[re_ind])*(re_ind - le_ind) 

        while (le_ind != re_ind):
            if (height[le_ind] < height[re_ind]):
                le_ind += 1
                vol_temp = min(height[le_ind], height[re_ind])*(re_ind - le_ind) 
            else:
                re_ind -= 1
                vol_temp = min(height[le_ind], height[re_ind])*(re_ind - le_ind) 
            vol = max(vol,vol_temp)
            
        return vol
        
```

<br><hr><br>

## 9. Palindrome Number
### Easy

<a href='https://leetcode.com/problems/palindrome-number/'>https://leetcode.com/problems/palindrome-number/</a>

Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

Example 1:
```
Input: 121
Output: true
```
Example 2:
```
Input: -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```
Example 3:
```
Input: 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```
Follow up:

Coud you solve it without converting the integer to a string?

<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 64 ms, faster than 95.72% of Python3 online submissions for Palindrome Number.<br>
Memory Usage: 13.2 MB, less than 83.12% of Python3 online submissions for Palindrome Number.</strong>
<br>

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        s = str(x)
        if (s[::-1]==s):
            return True
        return False
```

<br><hr><br>

## 8. String to Integer (atoi)
### Medium

<a href='https://leetcode.com/problems/string-to-integer-atoi/'>https://leetcode.com/problems/string-to-integer-atoi/</a>

Implement atoi which converts a string to an integer.

The function first discards as many whitespace characters as necessary until the first non-whitespace character is found. Then, starting from this character, takes an optional initial plus or minus sign followed by as many numerical digits as possible, and interprets them as a numerical value.

The string can contain additional characters after those that form the integral number, which are ignored and have no effect on the behavior of this function.

If the first sequence of non-whitespace characters in str is not a valid integral number, or if no such sequence exists because either str is empty or it contains only whitespace characters, no conversion is performed.

If no valid conversion could be performed, a zero value is returned.

Note:

Only the space character ' ' is considered as whitespace character.
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−2^31,  2^31 − 1]. If the numerical value is out of the range of representable values, INT_MAX (2^31 − 1) or INT_MIN (−2^31) is returned.
Example 1:
```
Input: "42"
Output: 42
```
Example 2:
```
Input: "   -42"
Output: -42
Explanation: The first non-whitespace character is '-', which is the minus sign.
             Then take as many numerical digits as possible, which gets 42.
```
Example 3:
```
Input: "4193 with words"
Output: 4193
Explanation: Conversion stops at digit '3' as the next character is not a numerical digit.
```
Example 4:
```
Input: "words and 987"
Output: 0
Explanation: The first non-whitespace character is 'w', which is not a numerical 
             digit or a +/- sign. Therefore no valid conversion could be performed.
```
Example 5:
```
Input: "-91283472332"
Output: -2147483648
Explanation: The number "-91283472332" is out of the range of a 32-bit signed integer.
             Thefore INT_MIN (−2^31) is returned.
```
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 36 ms, faster than 97.35% of Python3 online submissions for String to Integer (atoi).<br>
Memory Usage: 13.4 MB, less than 18.02% of Python3 online submissions for String to Integer (atoi).</strong>
<br>

```python
class Solution:
    def myAtoi(self, str: str) -> int:
        ind=0
        sign=1
        res=0
        
        for c in str:
            if (ind==0 and c==' '):
                next
            elif (ind==0 and c=='+'):
                ind=1
                next
            elif (ind==0 and c=='-'):
                ind=1
                sign=-1
                next
            elif (c.isdigit()==True):
                ind=1
                res = res*10 + int(c)
            else:
                break
        return max(min(sign*res,2**31-1),-2**31)
```

<br><hr><br>

## 7. Reverse Integer
### Easy

<a href='https://leetcode.com/problems/reverse-integer/'>https://leetcode.com/problems/reverse-integer/</a>

Given a 32-bit signed integer, reverse digits of an integer.

Example 1:
```
Input: 123
Output: 321
```
Example 2:
```
Input: -123
Output: -321
```
Example 3:
```
Input: 120
Output: 21
```
Note:
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−2^31,  2^31 − 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.
<br>
<hr>
<br>
<strong>My code result - Date unknown<br>Runtime: 40 ms, faster than 82.77% of Python3 online submissions for Reverse Integer.<br>
Memory Usage: 13.3 MB, less than 34.33% of Python3 online submissions for Reverse Integer.</strong>
<br>

```python
class Solution:
    def reverse(self, x: int) -> int:
        neg = False
        if (x < 0): 
            neg = True
            x = x * (-1)
        l = [x for x in str(x)]
        res = int(''.join(l[::-1]))
        if (neg == True): res = res * (-1)
        if (res < -2**31 or res > 2**31 -1): 
            return 0
        else:
            return res
```

<br><hr><br>


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
