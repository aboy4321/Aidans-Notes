Tags: #cs #leetcode #array
### Prompt
Given an array of integers `nums` and an integer `target`, return the indices `i` and `j` such that `nums[i] + nums[j] == target` and `i != j`.
### Intuition
We need to take in consideration both the indices and the values of those indices, I'm thinking we can use a dictionary and its key + value feature. 

With this, we should also use the `enumerate function` in a `for` loop so we can match the values in our array to the dictionary we will be using.
### My Solution

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        cache = {}
        for i,j in enumerate(nums):
            diff = target - j

            if diff in cache:
                return [cache[diff], i]
            
            cache[j] = i
```

