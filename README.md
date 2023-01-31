# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import numpy and sys module to use built-in functions for calculation.
2. Get input from the user for number of rows and add it by 1 for number of columns and by using np.zeros() set the matrix as null matrix. 
3. Using nested for loop find the ratio and perform the elementary row operations and find the final matrix. 
4. End the program.

## Program:
```python
Program to solve a matrix using Gaussian elimination with partial pivoting.
Developed by: E. VARSHA SHARON
RegisterNumber: 22004867

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero found')

    for j in range (i+1, n):
        ratio=a[j][i]/a[i][i]
        
        for k in range (n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
        
#back substitution
X[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    X[i]=a[i][n]
    
    for j in range (i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
        
    X[i]=X[i]/a[i][i]

for i in range(n):
    print('X%d = %0.2f'%(i,X[i]), end = ' ')
            
```

## Output:

![GAUSSIAN OUTPUT](https://user-images.githubusercontent.com/98278161/215656644-2989c91a-a9b9-4e03-bb5a-421a04f5658d.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

