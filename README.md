# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
Convert the given matrix into upper triangular form using row operations.

Eliminate lower elements by subtracting multiples of pivot rows.

Perform back substitution to find unknowns from last to first.

Display the solution values for all variables.
``` 

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: mahith m
RegisterNumber: 212225220061
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys

n = int(input())
a = np.zeros((n, n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x[n-1] = a[n-1][n] / a[n-1][n-1]

for i in range(n-2, -1, -1):
    x[i] = a[i][n]
    for j in range(i+1, n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i] / a[i][i]

for i in range(n):
    print('X%d = %0.2f' % (i, x[i]), end=' ')
```

## Output:
<img width="575" height="792" alt="Screenshot 2026-05-27 090509" src="https://github.com/user-attachments/assets/e0a7c9fa-791c-4e50-ac48-93b94ae1f9e9" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

