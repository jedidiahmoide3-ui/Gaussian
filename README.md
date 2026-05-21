# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1. Read the order of the matrix and the augmented matrix values as input.
2. Convert the augmented matrix into an upper triangular matrix using forward elimination.
3. Apply back substitution to calculate the values of the unknown variables.
4. Display the solution of the system of equations.


## Program:
/*

Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Jedidiah M D
RegisterNumber: 212225230116

*/
```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def solve_guassian(data):
    n=int(data[0])
    a=np.array(data[1:],dtype=float).reshape(n,n+1)
    for i in range(n):
        for j in range(i+1,n):
            factor=a[j,i]/a[i,i]
            a[j]-=factor*a[i]
    x=np.zeros(n)        
    for i in range(n-1,-1,-1):
        x[i]=(a[i,-1]-np.dot(a[i,i+1:n],x[i+1:n]))/a[i,i]
    return x
data=[]    
for i in range(13):
    data.append(input())
result=solve_guassian(data)    
print("".join([f"X{i} = {val:.2f} "for i,val in enumerate(result)]))
```
## Output:
<img width="732" height="408" alt="image" src="https://github.com/user-attachments/assets/27f935f9-6389-4782-ba38-5325bc36cc4c" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

