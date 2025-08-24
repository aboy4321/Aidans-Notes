Tags: #cs #leetcode #math 
### Prompt
Given an $m\times n$ matrix, return all elements of the matrix in spiral order
### Intuition
Based off the spiral shape shown to us, we would know that our $x$ value would be changing first while the $y$ value stays the same, but after hitting the end of that side of the matrix, their roles reverse.

From right to down thew value of our $x$ stays constant while our $y$ increases. We would want to continue this cycle until the next direction would put us at a number we have already seen before, we would then want to just immediately change to the next given direction.

We could as well approach this in a way where we use pointers, those pointers allowing us to change direction based off the boundaries we have touched so far.

The pointers would shift the placement of each of our boundaries, i.e we could shift our bottom boundary one place higher after we hit our left boundary. When pointers reach one another we are able to stop the algorithm, like if the bottom, pointer reached the top, we shift the top pointer down onto the current bottom pointer.

### My Solution
Two-Pointer approach:
```Python
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        # Pointers
        rows, cols = len(matrix), len(matrix[0])
        x, y, dx, dy = 0, 0, 1, 0
        res = []
		# Iterate through Matrix, appending seen items to our list and transforming seen values to dummy elements
        for _ in range(rows * cols):
            res.append(matrix[y][x])
            matrix[y][x] = "."
			# Checks bounds, if bounds are met or seen value is caught then direction is changed
            if not 0 <= x + dx < cols or not 0 <= y + dy < rows or matrix[y+dy][x+dx] == ".":
                dx, dy = -dy, dx
            
            x += dx
            y += dy
        # Returning the spiral matrix
        return res
```
