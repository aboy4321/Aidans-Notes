Tags: #cs #leetcode #array 
### Prompt
Given two strings `s` and `t`, return `true` if the two strings are anagrams of each other, otherwise return `false`.

An anagram is a string that contains the exact same characters as another string, but the order of the characters can be different.
### Intuition
My immediate thought is we would know if two strings are anagrams if they have the same length (base case) and if they each have the same number of letters (same a's, b's etc.). We would need to find some way to count the number of unique characters, I think we should use a hash table `{}` and in this case we would want to use two and compare them to see if they are the same as one another.
### My Solution

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
	    if len(s) != len(t):
		    return False
		s_count, t_count = {}, {}

		for i in range(len(s)):
			s_count[s[i]] = 1 + s_count.get(s[i], 0)
			t_count[t[i]] = 1 + t_count.get(t[i], 0)
		return s_count == t_count
``` 

