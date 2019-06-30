# LeetCode

Runtime Statistics:<br>
Top 0-20%   : 9 times   <br>
Top 20-40%  : 3 time    <br>
Top 40-60%  : 3 times    <br>
Top 60-80%  : 1 time    <br>
Top 80-100% : 15 times   <br>
Total: 30 questions accepted <br>

Questions:<br>
[(Medium) 2. Add Two Numbers](https://github.com/daydreamersjp/LeetCode#2-add-two-numbers)<br>
[(Medium) 3. Longest Substring Without Repeating Characters](https://github.com/daydreamersjp/LeetCode#3-longest-substring-without-repeating-characters)<br>
[(Medium) 5. Longest Palindromic Substring](https://github.com/daydreamersjp/LeetCode#5-longest-palindromic-substring)<br>
[(Medium) 6. ZigZag Conversion](https://github.com/daydreamersjp/LeetCode#6-zigzag-conversion)<br>
[(Easy) 7. Reverse Integer](https://github.com/daydreamersjp/LeetCode#7-reverse-integer)<br>
[(Medium) 8. String to Integer (atoi)](https://github.com/daydreamersjp/LeetCode#8-string-to-integer-atoi)<br>
[(Easy) 9. Palindrome Number](https://github.com/daydreamersjp/LeetCode#9-palindrome-number)<br>
[(Medium) 11. Container With Most Water](https://github.com/daydreamersjp/LeetCode#11-container-with-most-water)<br>
[(Medium) 12. Integer to Roman](https://github.com/daydreamersjp/LeetCode#12-integer-to-roman)<br>
[(Easy) 13. Roman to Integer](https://github.com/daydreamersjp/LeetCode#13-roman-to-integer)<br>
[(Easy) 14. Longest Common Prefix](https://github.com/daydreamersjp/LeetCode#14-longest-common-prefix)<br>
[(Medium) 16. 3Sum Closest](https://github.com/daydreamersjp/LeetCode#16-3sum-closest)<br>
[(Medium) 17. Letter Combinations of a Phone Number](https://github.com/daydreamersjp/LeetCode#17-letter-combinations-of-a-phone-number)<br>
[(Medium) 18. 4Sum](https://github.com/daydreamersjp/LeetCode#18-4sum)<br>
[(Easy) 20. Valid Parentheses](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#20-valid-parentheses)<br>
[(Easy) 21. Merge Two Sorted Lists](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#21-merge-two-sorted-lists)<br>
[(Medium) 22. Generate Parentheses](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#22-generate-parentheses)<br>
[(Medium) 24. Swap Nodes in Pairs](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#24-swap-nodes-in-pairs)<br>
[(Easy) 26. Remove Duplicates from Sorted Array](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#26-remove-duplicates-from-sorted-array)<br>
[(Easy) 27. Remove Element](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#27-remove-element)<br>
[(Easy) 28. Implement strStr()](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#28-implement-strstr)<br>
[(Medium) 31. Next Permutation](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#31-next-permutation)<br>
[(Medium) 33. Search in Rotated Sorted Array](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#33-search-in-rotated-sorted-array)<br>
[(Medium) 34. Find First and Last Position of Element in Sorted Array](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#34-find-first-and-last-position-of-element-in-sorted-array)<br>
[(Easy) 35. Search Insert Position](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#35-search-insert-position)<br>
[(Medium) 36. Valid Sudoku](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#36-valid-sudoku)<br>
[(Easy) 38. Count and Say](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#38-count-and-say)<br>
[(Medium) 39. Combination Sum](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#39-combination-sum)<br>
[(Medium) 40. Combination Sum II](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#40-combination-sum-ii)<br>
[(Medium) 43. Multiply Strings](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#43-multiply-strings)<br>
[(Medium) 46. Permutations](https://github.com/daydreamersjp/LeetCode/blob/master/README.md#46-permutations)<br>

<hr>

## 46. Permutations
### Medium

<a href='https://leetcode.com/problems/permutations/'>https://leetcode.com/problems/permutations/</a>

Given a collection of distinct integers, return all possible permutations.

Example:

```
Input: [1,2,3]
Output:
[
  [1,2,3],
  [1,3,2],
  [2,1,3],
  [2,3,1],
  [3,1,2],
  [3,2,1]
]
```

<br>
<hr>
<br>

<strong>My code result - 2019/06/30 16:56PM<br>Runtime: 64 ms, faster than 15.36% of Python3 online submissions for Permutations.
<br>Memory Usage: 13.5 MB, less than 8.95% of Python3 online submissions for Permutations.</strong>
<br>

```python
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        if len(nums)==1:
            return [nums]
        
        res = []
        
        for i,x in enumerate(nums):
            for res_p in self.permute(nums[:i]+nums[i+1:]):
                res += [ [x] + res_p ]
        
        return res
```
<br>
<hr>
<br>

#### Commment:

This problem should not use recursive program. 

<br><hr><br>


## 43. multiply Strings
### Medium

<a href='https://leetcode.com/problems/multiply-strings/'>https://leetcode.com/problems/multiply-strings/</a>

Given two non-negative integers num1 and num2 represented as strings, return the product of num1 and num2, also represented as a string.

Example 1:
```
Input: num1 = "2", num2 = "3"
Output: "6"
```
Example 2:
```
Input: num1 = "123", num2 = "456"
Output: "56088"
```
Note:

The length of both num1 and num2 is < 110.
Both num1 and num2 contain only digits 0-9.
Both num1 and num2 do not contain any leading zero, except the number 0 itself.
You must not use any built-in BigInteger library or convert the inputs to integer directly.

<br>
<hr>
<br>

<strong>My code result - 2019/06/09 10:19PM<br>Runtime: 44 ms, faster than 79.40% of Python3 online submissions for Multiply Strings.
<br>Memory Usage: 13.3 MB, less than 22.43% of Python3 online submissions for Multiply Strings.</strong>
<br>

```python
class Solution:
    def multiply(self, num1: str, num2: str) -> str:
        dc = '0123456789'              
        return self.convInt2Str(dc, self.convStr2Int(dc, num1)*self.convStr2Int(dc, num2) )
        
    def convStr2Int(self, dc, nums):
        if len(nums)==1: 
            return dc.index(nums)
        else: 
            return dc.index(nums[len(nums)-1]) + 10 * self.convStr2Int(dc,nums[:-1])
    
    def convInt2Str(self, dc, num):
        if (num//10==0): 
            return dc[num]
        else:
            return self.convInt2Str(dc, num // 10) + dc[num % 10]
```

<br><hr><br>

## 40. Combination Sum II
### Medium

<a href='https://leetcode.com/problems/combination-sum-ii/'>https://leetcode.com/problems/combination-sum-ii/</a>

Given a collection of candidate numbers (candidates) and a target number (target), find all unique combinations in candidates where the candidate numbers sums to target.

Each number in candidates may only be used once in the combination.

Note:

All numbers (including target) will be positive integers.
The solution set must not contain duplicate combinations.
Example 1:
```
Input: candidates = [10,1,2,7,6,1,5], target = 8,
A solution set is:
[
  [1, 7],
  [1, 2, 5],
  [2, 6],
  [1, 1, 6]
]
```
Example 2:
```
Input: candidates = [2,5,2,1,2], target = 5,
A solution set is:
[
  [1,2,2],
  [5]
]
```
<br>
<hr>
<br>

<strong>My code result - 2019/06/08 2:15AM<br>Runtime: 120 ms, faster than 31.36% of Python3 online submissions for Combination Sum II.
<br>Memory Usage: 13.2 MB, less than 43.57% of Python3 online submissions for Combination Sum II.</strong>
<br>

```python
class Solution:
    def combinationSum2(self, c, t):
        ##
        ## c: List[int]
        ## t: int   
        ## -> List[List[int]]
        
        if (len(c)==0): return []
        if (min(c) > t): return []
        
        res = []
        c.sort()
        for n in range(len(c)):
            if (sum(c[:n+1]) <= t):
                for r in self.combSumBy(c,t,n+1):
                    if (r not in res): 
                        res += [r]
            else:
                break
        
        return res

    
    def combSumBy(self,c,t,n):
        c.sort()
        if (sum(c[:n])>t): return []
        
        res = []
        if (n==1):
            for v in c:
                if (v > t): break
                elif (v==t and ([v] not in res)):
                    res += [[v]]
        else:
            for i,v in enumerate(c):
                rec = self.combSumBy(c[i+1:],t-v,n-1)
                res += [ [c[i]] + r for r in rec if r not in res]
        return res
```

<br><hr><br>

## 39. Combination Sum
### Medium

<a href='https://leetcode.com/problems/combination-sum/'>https://leetcode.com/problems/combination-sum/</a>

Given a set of candidate numbers (candidates) (without duplicates) and a target number (target), find all unique combinations in candidates where the candidate numbers sums to target.

The same repeated number may be chosen from candidates unlimited number of times.

Note:

All numbers (including target) will be positive integers.
The solution set must not contain duplicate combinations.
Example 1:
```
Input: candidates = [2,3,6,7], target = 7,
A solution set is:
[
  [7],
  [2,2,3]
]
```
Example 2:
```
Input: candidates = [2,3,5], target = 8,
A solution set is:
[
  [2,2,2,2],
  [2,3,3],
  [3,5]
]
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 152 ms, faster than 16.97% of Python3 online submissions for Combination Sum.
<br>Memory Usage: 13.3 MB, less than 37.40% of Python3 online submissions for Combination Sum.</strong>
<br>

```python
class Solution:
    def combinationSum(self, c: List[int], t: int) -> List[List[int]]:
        if (len(c)==0): return []
        if (min(c)>t): return []
        
        if (len(c)==1):
            if (t % c[0] == 0): return [[c[0]]*(t // c[0])]       
        
        res = []
        if ((t % max(c)) == 0): 
            res +=  [[max(c)]*(t // max(c))]
        for i in range(0,(t // max(c)) + 1):
            t0 = t - i * max(c)
            c0 = [v for v in c]
            c0.remove(max(c))
            res0 = self.combinationSum(c0, t0)
            r0 = [sorted(r + [max(c)]*i) for r in res0]
            for r in r0:
                if (r not in res):
                    res += [r]
        
        return res
```

<br><hr><br>

## 38. Count and Say
### Easy

<a href='https://leetcode.com/problems/count-and-say/'>https://leetcode.com/problems/count-and-say/</a>

The count-and-say sequence is the sequence of integers with the first five terms as following:
```
1.     1
2.     11
3.     21
4.     1211
5.     111221
```
1 is read off as "one 1" or 11.
11 is read off as "two 1s" or 21.
21 is read off as "one 2, then one 1" or 1211.

Given an integer n where 1 ≤ n ≤ 30, generate the nth term of the count-and-say sequence.

Note: Each term of the sequence of integers will be represented as a string.

 

Example 1:
```
Input: 1
Output: "1"
```
Example 2:
```
Input: 4
Output: "1211"
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 40 ms, faster than 87.77% of Python3 online submissions for Count and Say.
<br>Memory Usage: 13 MB, less than 88.84% of Python3 online submissions for Count and Say.</strong>
<br>

```python
class Solution:
    def countAndSay(self, n: int) -> str:
        if n==1: 
            return '1'
            
        res = '1'        
        for _ in range(1,n):
            res = self.countAndSayIter(res)
        
        return res      
    
    def countAndSayIter(self, str0):
       
        res = ''
        i = 1
        c = str0[0]
        n = 1
        while (i<len(str0)):
            if (str0[i-1]==str0[i]): 
                n += 1
            else: 
                res += str(n) + c
                c = str0[i]
                n = 1
            i += 1
        res += str(n) + c
        
        return res  
```

<br><hr><br>

## 36. Valid Sudoku
### Medium

<a href='https://leetcode.com/problems/valid-sudoku/'>https://leetcode.com/problems/valid-sudoku/</a>

Determine if a 9x9 Sudoku board is valid. Only the filled cells need to be validated according to the following rules:

1.Each row must contain the digits 1-9 without repetition.
2.Each column must contain the digits 1-9 without repetition.
3.Each of the 9 3x3 sub-boxes of the grid must contain the digits 1-9 without repetition.

![](./img/250px-Sudoku-by-L2G-20050714.svg.png)

A partially filled sudoku which is valid.

The Sudoku board could be partially filled, where empty cells are filled with the character '.'.

Example 1:
```
Input:
[
  ["5","3",".",".","7",".",".",".","."],
  ["6",".",".","1","9","5",".",".","."],
  [".","9","8",".",".",".",".","6","."],
  ["8",".",".",".","6",".",".",".","3"],
  ["4",".",".","8",".","3",".",".","1"],
  ["7",".",".",".","2",".",".",".","6"],
  [".","6",".",".",".",".","2","8","."],
  [".",".",".","4","1","9",".",".","5"],
  [".",".",".",".","8",".",".","7","9"]
]
Output: true
```
Example 2:
```
Input:
[
  ["8","3",".",".","7",".",".",".","."],
  ["6",".",".","1","9","5",".",".","."],
  [".","9","8",".",".",".",".","6","."],
  ["8",".",".",".","6",".",".",".","3"],
  ["4",".",".","8",".","3",".",".","1"],
  ["7",".",".",".","2",".",".",".","6"],
  [".","6",".",".",".",".","2","8","."],
  [".",".",".","4","1","9",".",".","5"],
  [".",".",".",".","8",".",".","7","9"]
]
Output: false
Explanation: Same as Example 1, except with the 5 in the top left corner being 
    modified to 8. Since there are two 8's in the top left 3x3 sub-box, it is invalid.
```
Note:

A Sudoku board (partially filled) could be valid but is not necessarily solvable.
Only the filled cells need to be validated according to the mentioned rules.
The given board contain only digits 1-9 and the character '.'.
The given board size is always 9x9.

<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 72 ms, faster than 16.82% of Python3 online submissions for Valid Sudoku.
<br>Memory Usage: 13.3 MB, less than 10.22% of Python3 online submissions for Valid Sudoku.</strong>
<br>

```python
import collections

class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        for i in range(9):
            if (self.judgeValid(board[i])==False): return False
            if (self.judgeValid([board[j][i] for j in range(9)])==False): return False
        for i in range(3):
            for j in range(3):
                if (self.judgeValid(board[0+j*3][0+i*3:3+i*3]+board[1+j*3][0+i*3:3+i*3]+board[2+j*3][0+i*3:3+i*3])==False): return False
        
        return True
        
        
        
    def judgeValid(self, nums):
        dc = collections.Counter(nums)
        for k,v in dc.items():
            if (v > 1 and k != '.'): return False
        return True
```

<br><hr><br>

## 35. Search Insert Position
### Easy

<a href='https://leetcode.com/problems/search-insert-position/'>https://leetcode.com/problems/search-insert-position/</a>

Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You may assume no duplicates in the array.

Example 1:
```
Input: [1,3,5,6], 5
Output: 2
```
Example 2:
```
Input: [1,3,5,6], 2
Output: 1
```
Example 3:
```
Input: [1,3,5,6], 7
Output: 4
```
Example 4:
```
Input: [1,3,5,6], 0
Output: 0
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 36 ms, faster than 87.98% of Python3 online submissions for Search Insert Position.
<br>Memory Usage: 13.6 MB, less than 77.10% of Python3 online submissions for Search Insert Position.</strong>
<br>

```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        if nums==[]: return 0
        if nums[0]>=target: return 0
        if nums[-1]<target: return len(nums)
        
        for i in range(len(nums)-1):
            if (nums[i]<target and nums[i+1]>=target): return i+1
```

<br><hr><br>

## 34. Find First and Last Position of Element in Sorted Array
### Medium

<a href='https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/'>https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/</a>

Given an array of integers nums sorted in ascending order, find the starting and ending position of a given target value.

Your algorithm's runtime complexity must be in the order of O(log n).

If the target is not found in the array, return [-1, -1].

Example 1:
```
Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```
Example 2:
```
Input: nums = [5,7,7,8,8,10], target = 6
Output: [-1,-1]
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 32 ms, faster than 98.34% of Python3 online submissions for Find First and Last Position of Element in Sorted Array.<br>
Memory Usage: 13.8 MB, less than 64.49% of Python3 online submissions for Find First and Last Position of Element in Sorted Array.</strong>
<br>

```python
class Solution:
    def searchRange(self, nums: List[int], target: int) -> List[int]:
        if (nums==[]): return [-1,-1]
        if (len(nums)==1):
            if (nums[0]==target): return [0,0]
            else: return [-1,-1]
            
        low = 0 
        high = len(nums)-1
        
        while (low<=high):
            mid = (low+high) // 2
            if (nums[mid]==target):
                i, j = 0, 0
                while (mid-i-1>=low):
                    if (nums[mid-i-1]==target):
                        i += 1
                    else:
                        break
                while (mid+j+1<=high):
                    if (nums[mid+j+1]==target):
                        j += 1
                    else:
                        break
                return [mid-i,mid+j]
            
            elif (nums[mid]>target):
                high = mid - 1
            else:
                low = mid + 1
        
        return [-1,-1]
```

<br><hr><br>

## 33. Search in Rotated Sorted Array
### Medium

<a href='https://leetcode.com/problems/search-in-rotated-sorted-array/'>https://leetcode.com/problems/search-in-rotated-sorted-array/</a>

Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.

(i.e., [0,1,2,4,5,6,7] might become [4,5,6,7,0,1,2]).

You are given a target value to search. If found in the array return its index, otherwise return -1.

You may assume no duplicate exists in the array.

Your algorithm's runtime complexity must be in the order of O(log n).

Example 1:
```
Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4
```
Example 2:
```
Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 32 ms, faster than 96.22% of Python3 online submissions for Search in Rotated Sorted Array.<br>
Memory Usage: 13.1 MB, less than 86.31% of Python3 online submissions for Search in Rotated Sorted Array.</strong>
<br>

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        if (nums==[]): return -1
        
        low = 0
        high = len(nums) - 1
        mid = (low + high) // 2
        #1st half: nums[0:mid]
        #2nd half: nums[mid:]
        
        if (high==0):
            if (nums[high]==target): return high
            else: return -1
        if (high==1):
            if (nums[high]==target): return high
            if (nums[0]==target): return 0
            else: return -1
        
        #Pivot is 2nd half
        if (nums[0]==sorted(nums[0:mid])[0]):
            if (nums[0]>target or nums[mid-1]<target):
                #target is possibly in 2nd half
                if (self.search(nums[mid:], target)==-1):
                    return -1
                else:
                    return mid + self.search(nums[mid:], target)
            else:
                if (self.binSearch(nums[0:mid], target)==-1):
                    return -1
                else:
                    return self.binSearch(nums[0:mid], target)
                
        #Pivot is 1st half
        else:
            if (nums[mid]>target or nums[len(nums)-1]<target):
                #target is possibly in 1st half
                if (self.search(nums[0:mid], target)==-1):
                    return -1
                else:
                    return self.search(nums[0:mid], target)
            else:
                if (self.binSearch(nums[mid:], target)==-1):
                    return -1
                else:
                    return mid + self.binSearch(nums[mid:], target)
        
        
    def binSearch(self, nums, target):
        low = 0
        high = len(nums) - 1
        
        while (low <= high):
            mid = (low + high) // 2
            if (nums[mid]==target):
                return mid
            elif nums[mid] > target:
                high = mid - 1
            else:
                low = mid + 1
        return -1 
```

<br><hr><br>


## 31. Next Permutation
### Medium

<a href='https://leetcode.com/problems/next-permutation/'>https://leetcode.com/problems/next-permutation/</a>

Implement next permutation, which rearranges numbers into the lexicographically next greater permutation of numbers.

If such arrangement is not possible, it must rearrange it as the lowest possible order (ie, sorted in ascending order).

The replacement must be in-place and use only constant extra memory.

Here are some examples. Inputs are in the left-hand column and its corresponding outputs are in the right-hand column.
```
1,2,3 → 1,3,2
3,2,1 → 1,2,3
1,1,5 → 1,5,1
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 72 ms, faster than 6.42% of Python3 online submissions for Next Permutation.
<br>Memory Usage: 13.3 MB, less than 12.71% of Python3 online submissions for Next Permutation.</strong>
<br>

```python
class Solution:
    def nextPermutation(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        
        if (len(nums) <= 1): 
            return
        if (len(nums) == 2):
            nums[0], nums[1] = nums[1], nums[0]
            return
        if (nums == sorted(nums,reverse=True)):
            nums.sort()
            return
        
        nums1 = nums[1:]
        if (nums1==sorted(nums1,reverse=True)): 
            for i,l in enumerate(sorted(nums1)):
                if nums[0] < l:
                    nums[:] = [l] + sorted([nums[0]] + sorted(nums1)[:i]+sorted(nums1)[i+1:])
                    break
            return
        else:
            self.nextPermutation(nums1)
            nums[:] = [nums[0]] + nums1
            return 
```

<br><hr><br>

## 28. Implement strStr()
### Easy

<a href='https://leetcode.com/problems/implement-strstr/'>https://leetcode.com/problems/implement-strstr/</a>

Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

Example 1:
```
Input: haystack = "hello", needle = "ll"
Output: 2
```
Example 2:
```
Input: haystack = "aaaaa", needle = "bba"
Output: -1
```
Clarification:

What should we return when needle is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 28 ms, faster than 99.12% of Python3 online submissions for Implement strStr().
<br>Memory Usage: 13.1 MB, less than 98.23% of Python3 online submissions for Implement strStr().</strong>
<br>

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        
        if (needle == ''): return 0
        
        for i in range(len(haystack)-len(needle)+1):
            if (self.strStart(haystack[i:],needle)==True): return i
        
        return -1
                      
    def strStart(self, h0, n0) -> bool:
        if (len(h0) < len(n0) or h0=='' or n0==''): return False
        if (h0[0:len(n0)] == n0): return True
        return False
```

<br><hr><br>

## 27. Remove Element
### Easy

<a href='https://leetcode.com/problems/remove-element/'>https://leetcode.com/problems/remove-element/</a>

Given an array nums and a value val, remove all instances of that value in-place and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

Example 1:
```
Given nums = [3,2,2,3], val = 3,

Your function should return length = 2, with the first two elements of nums being 2.

It doesn't matter what you leave beyond the returned length.
```
Example 2:
```
Given nums = [0,1,2,2,3,0,4,2], val = 2,

Your function should return length = 5, with the first five elements of nums containing 0, 1, 3, 0, and 4.

Note that the order of those five elements can be arbitrary.

It doesn't matter what values are set beyond the returned length.
```
Clarification:

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by reference, which means modification to the input array will be known to the caller as well.

Internally you can think of this:
```
// nums is passed in by reference. (i.e., without making a copy)
int len = removeElement(nums, val);

// any modification to nums in your function would be known by the caller.
// using the length returned by your function, it prints the first len elements.
for (int i = 0; i < len; i++) {
    print(nums[i]);
}
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 36 ms, faster than 88.82% of Python3 online submissions for Remove Element.
<br>Memory Usage: 13.2 MB, less than 47.82% of Python3 online submissions for Remove Element.</strong>
<br>

```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        if len(nums)==0: return 0
        
        i = 0
        j = 0
        for j in range(len(nums)):
            if nums[j] != val:
                nums[i] = nums[j]
                i += 1
        
        return i
```

<br><hr><br>

## 26. Remove Duplicates from Sorted Array
### Easy

<a href='https://leetcode.com/problems/remove-duplicates-from-sorted-array/'>https://leetcode.com/problems/remove-duplicates-from-sorted-array/</a>

Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

Example 1:
```
Given nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.

It doesn't matter what you leave beyond the returned length.
```
Example 2:
```
Given nums = [0,0,1,1,1,2,2,3,3,4],

Your function should return length = 5, with the first five elements of nums being modified to 0, 1, 2, 3, and 4 respectively.

It doesn't matter what values are set beyond the returned length.
```
Clarification:

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by reference, which means modification to the input array will be known to the caller as well.

Internally you can think of this:
```
// nums is passed in by reference. (i.e., without making a copy)
int len = removeDuplicates(nums);

// any modification to nums in your function would be known by the caller.
// using the length returned by your function, it prints the first len elements.
for (int i = 0; i < len; i++) {
    print(nums[i]);
}
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 92 ms, faster than 13.49% of Python3 online submissions for Remove Duplicates from Sorted Array.<br>Memory Usage: 14.9 MB, less than 15.29% of Python3 online submissions for Remove Duplicates from Sorted Array.</strong>
<br>

```python
from collections import Counter 
class Solution:
#     def removeDuplicates(self, nums: List[int]) -> int:
#         if len(nums)==0: return 0
#         numsdict = Counter(nums)
#         for k,v in numsdict.items():
#             if v > 1:
#                 for _ in range(v-1):
#                     nums.remove(k)
        
#         return len(nums)
    
    def removeDuplicates(self, nums):
        i = 0
        while i < len(nums)-1:
            if nums[i] == nums[i+1]:
                del nums[i]
            else:
                i += 1
        return len(nums)
```

<br><hr><br>

## 24. Swap Nodes in Pairs
### Medium

<a href='https://leetcode.com/problems/swap-nodes-in-pairs/'>https://leetcode.com/problems/swap-nodes-in-pairs/</a>

Given a linked list, swap every two adjacent nodes and return its head.

You may not modify the values in the list's nodes, only nodes itself may be changed.

 

Example:
```
Given 1->2->3->4, you should return the list as 2->1->4->3.
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 36 ms, faster than 88.64% of Python3 online submissions for Swap Nodes in Pairs.
<br>Memory Usage: 13 MB, less than 88.19% of Python3 online submissions for Swap Nodes in Pairs.</strong>
<br>

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def swapPairs(self, head: ListNode) -> ListNode:
        pre, pre.next = self, head
        while pre.next and pre.next.next:
            a = pre.next
            b = pre.next.next
            pre.next, a.next, b.next = b, b.next, a
            pre = a
        return self.next
```

<br><hr><br>


## 22. Generate Parentheses
### Medium

<a href='https://leetcode.com/problems/generate-parentheses/'>https://leetcode.com/problems/generate-parentheses/</a>
Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

For example, given n = 3, a solution set is:
```
[
  "((()))",
  "(()())",
  "(())()",
  "()(())",
  "()()()"
]
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 76 ms, faster than 6.84% of Python3 online submissions for Generate Parentheses.
<br>Memory Usage: 13.3 MB, less than 71.57% of Python3 online submissions for Generate Parentheses.</strong>
<br>

```python
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        if (n==0): return [""]
        if (n==1): return["()"]
               
        res = []
  
        for i in range(1,int(n/2)+1):
            for x in self.generateParenthesis(n-i):
                for y in self.generateParenthesis(i):
                    if (x+y not in res):
                        res += [x+y]
                    if (y+x not in res):
                        res += [y+x]
                if ("("*i+x+")"*i not in res):
                    res += ["("*i+x+")"*i]

        return res
```

<br><hr><br>


## 21. Merge Two Sorted Lists
### Easy

<a href='https://leetcode.com/problems/merge-two-sorted-lists/'>https://leetcode.com/problems/merge-two-sorted-lists/</a>

Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

Example:
```
Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4
```
<br>
<hr>
<br>

<strong>My code result - Date unknown<br>Runtime: 36 ms, faster than 98.29% of Python3 online submissions for Merge Two Sorted Lists.
<br>Memory Usage: 13.3 MB, less than 12.33% of Python3 online submissions for Merge Two Sorted Lists.</strong>
<br>

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
       
        if l1 and l2:
            if l1.val > l2.val:
                l1, l2 = l2, l1
            l1.next = self.mergeTwoLists(l1.next, l2)
        return l1 or l2
```

<br><hr><br>

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

![](./img/200px-Telephone-keypad2.svg.png)

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
