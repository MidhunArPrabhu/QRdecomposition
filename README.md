# EXPERIMENT-08
# ALGORITHIM FOR QR-DECOMPOSITION
## AIM :

To implement QR decomposition algorithm using the Gram-Schmidt method.

## EQUIPMENTS REQUIRED :
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## ALGORITHIM :

1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
      ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R

      ![eqn5](./ex2.jpg)



## PROGRAM :
### GRAM-SCHMIDT METHOD :
```python

''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: MIDHUN AZHAHU RAJA P
RegisterNumber: 22008311
'''python
import numpy as np
def QR_Decomposition(A):
    n, m = A.shape
    Q = np.empty((n, n))
    u = np.empty((n, n))
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    for i in range(1, n):
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j]
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
    R = np.zeros((n, m))
    for i in range(n):
        for j in range(i, m):
            R[i, j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)

a = np.array(eval(input()))
QR_Decomposition(a) 
```

## OUTPUT :

![image](https://user-images.githubusercontent.com/118054670/214362153-03f576a9-fe65-4b1c-8521-84e98a49a16d.png)


## RESULT :

Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
