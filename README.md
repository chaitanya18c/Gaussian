# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the numpy module to use the built-in functions for calculation.
2. Import the sys module to use the built-in functions.
3. Get input from the user for number of rows and add it by 1 for number of columns
4. Using np.zeros() set the matrix as null matrix
5. Using nested for loop get input from the user for each element in the matrix
6. Using nested for loop find the ratio and perform the elementary row operations and find
the final matrix
7. Use back substitution method to find the value of the variables and print it.
8. End the program

## Program:
    '''Program to solve a matrix using Gaussian elimination with partial pivoting.
    Developed by: CHAITANYA P S
    RegisterNumber: 212222230024
    '''
    import numpy as np
    import sys

    n=int(input())
    a=np.zeros((n,n+1))
    x=np.zeros(n)

    for i in range(n):
        for j in range(n+1):
            a[i][j]=float(input())
        
    for i in range(n):
        for j in range(i+1,n):
            ratio=a[j][i]/a[i][i]
        
            for k in range(n+1):
                a[j][k]=a[j][k]-ratio*a[i][k]
    x[n-1]=a[n-1][n]/a[n-1][n-1]

    for i in range(n-2,-1,-1):
        x[i]=a[i][n]
        for j in range(i+1,n):
            x[i]=x[i]-a[i][j]*x[j]
        
        x[i]=x[i]/a[i][i]
    
    for i in range(n):
        print("X%d = %0.2f" %(i,x[i]),end=" ")

## Output:
![gaussian elimination](https://github.com/chaitanya18c/Gaussian/assets/119392724/58a17f42-01c6-4c3d-af4c-5f4559243718)
![gaussian elimaination](https://github.com/chaitanya18c/Gaussian/assets/119392724/0440d9ad-9d9e-4afd-9d82-16bc741c39b5)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

