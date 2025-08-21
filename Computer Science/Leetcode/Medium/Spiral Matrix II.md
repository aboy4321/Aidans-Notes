Tags: #cs #leetcode #math 
### Prompt
Given a positive integer $n$, generate an $n \times n$ matrix filled with elements from $1$ to $n^2$ in spiral order.
### Intuition
As this is the continuation of the [[Spiral Matrix]] problem, the answer is intuitively very close to the original problem. 

Firstly using a `for`- loop would help us generate an empty matrix of size $n \times n$, then just like our previous solution for [[Spiral Matrix]], we define an $x,y,dx$ and $dy$ variable which represent our current positions and the change in position due to increasing proximity to the bounds of the matrix. Since this spiral starts from left to right, we would at least want to again say `dx = 1` at the beginning.
### My Solution
``` python
class Solution:
    def generateMatrix(self, n: int) -> List[List[int]]:
		# Generating empty matrix
		matrix  = [[0] * n for _ in range(n)]
		# Defining current position and change of position values 
		x, y, dx, dy = 0, 0, 1, 0
		current = 1
		# Looping through matrix
		for _ in range(n**2):
			matrix[y][x] = current
			current += 1
			# Checking if loop reaches bounds
			if not 0 <= x+dx < n or not 0 <= y+dy < n or matrix[y+dy][x+dx] != 0:
				dx, dy = -dy, dx
			x += dx
			y += dy
		return matrix  
```

