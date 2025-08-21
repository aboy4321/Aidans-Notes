Tags: #math #cs #python
### Definition
A matrix is a method of organizing numbers in a rectangular grid defined by a number of rows and columns. We define the size of a matrix by the number of rows $m$ and columns $n$.
### Uses
Matrices are used to solve linear equations, represent data, transform images, and (very useful for Python) for machine learning algorithms
### Example
Matrix addition using a for-loop:
```python
x = [[1, 2, 3],[4, 5, 6],[7, 8, 9]]
y = [[9, 8, 7],[6, 5, 4],[3, 2, 1]]
res = [[0]*3 for _ in range(3)]

for i in range(len(x)):
    for j in range(len(x[0])):
        res[i][j] = x[i][j] + y[i][j]

for r in res:
    print(r)
```





