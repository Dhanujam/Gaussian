# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Input the Number of Unknowns: Read the integer 𝑛( representing the number of unknowns.)

2.Initialize the Augmented Matrix: Create an 𝑛×(𝑛+1) matrix ,n×(n+1) matrix a initialized to zeros to store coefficients and constants. Create an array x of size 𝑛

3.Fill the Augmented Matrix:

4.Check for Zero on the Diagonal: Before proceeding with elimination, check if the diagonal element 𝑎[𝑖][𝑖]=0 a[i][i]=0. If true, terminate with an error message ("Divide by zero detected").

5.Forward Elimination (Pivot Row Processing):

6.Compute Row Elimination

7.Check for Singular Matrix

8.Back Substitution (Start from the Last Variable)

9.Iterative Back Substitution

10.Output the Solutions

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Dhanuja M
RegisterNumber: 212224230057
*/
```
```
def gaussian_elimination(matrix, n):
    for i in range(n):
        for j in range(i + 1, n):
            if matrix[i][i] == 0:
                raise ZeroDivisionError("Division by zero detected!")
            ratio = matrix[j][i] / matrix[i][i]
            for k in range(n + 1):
                matrix[j][k] -= ratio * matrix[i][k]
    x = [0 for _ in range(n)]
    for i in range(n - 1, -1, -1):
        x[i] = matrix[i][n]
        for j in range(i + 1, n):
            x[i] -= matrix[i][j] * x[j]
        x[i] /= matrix[i][i]
    
    return x
input_data = [
    3,
    1, 2, 4, 18,
    2, 12, -2, 9,
    5, 26, 5, 14
]
n = input_data[0]
matrix = []
idx = 1
for i in range(n):
    row = input_data[idx:idx + n + 1]
    matrix.append(row)
    idx += n + 1
solution = gaussian_elimination(matrix, n)
print(" ".join([f"X{i} = {val:.2f}" for i, val in enumerate(solution)]))
```

## Output:
![alt text](<Screenshot (41).png>)
![alt text](<Screenshot (42).png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

