# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### step-1 Input the augmented matrix of size n x (n+1) from the user.

### step-2 Forward Elimination: For each pivot row, eliminate the entries below the pivot using row operations.
   
### step-3 Check for Division by Zero: Exit if a pivot element is zero to avoid division by zero.

### step-4 Back Substitution: Start from the last row and solve for variables by substituting known values.
   
### step-5 Output the values of the variables X0, X1, ..., Xn-1.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Pralayakaveri Raja
RegisterNumber:212224230202 
'''
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
            sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end = ' ')
            
    

```

## Output:

![Screenshot 2025-04-24 212706](https://github.com/user-attachments/assets/179eed1c-e0cc-4e90-8bec-8753995be230)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

