# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: DHIYA D
RegisterNumber: 212225100012
'''
import numpy as np
def q(a):
    a=np.array(a,dtype=float)
    m,n=a.shape
    w=np.zeros((m,n))
    r=np.zeros((n,n))
    for j in range(n):
        v=a[:,j]
        for i in range(j):
            r[i,j]=np.dot(w[:,i],a[:,j])
            v=v-r[i,j]*w[:,i]
        r[j,j]=np.linalg.norm(v)
        w[:,j]=v/r[j,j]
    return w,r
    # Write your code 
a = np.array(eval(input()))
w,r=q(a)
print("The Q Matrix is\n",w)
print("The R Matrix is\n",r)


```

## Output
<img width="1042" height="421" alt="image" src="https://github.com/user-attachments/assets/0426de07-a655-4142-a3ce-4bfffa563505" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
