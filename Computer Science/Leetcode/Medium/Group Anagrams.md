Tags: #cs #leetcode #array 
### Prompt
Given an array of strings `strs`, group all anagrams together into sublists. You may return the output in any order.

An anagram is a string that contains the exact same characters as another string, but the order of the characters can be different.
### Intuition
We need to iterate through each string and compare them with one another, and if they are the same they will be added to a separate array.

A way we can compare them is by sorting the letters, since if they are anagrams, if sorted they should become the same string.

However, this is not very time efficient, so lets try a different way.

We are also able to count the letters of a string and check based on if string `a` has 3 A's and 2 B's and string `b` has the same number, then they are anagrams and should go into the same set.

We would want to use a hash-map, but more specifically the `defaultdict(list)` function in Python, as it will be able to handle our edge cases without raising a `KeyError`. 
### My Solution

```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        # Initializing dictionary 
        sol = defaultdict(list)
        # iterating thru strings
        for s in strs:
	        # creating empty count array
            count = [0] * 26
            # iterating thru characters in string
            for c in s:
                count[ord(c) - ord('a')] += 1
            sol[tuple(count)].append(s)
        return list(sol.values())
```

