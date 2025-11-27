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
```import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    q=np.empty((n,m))
    u=np.empty((n,m))
    r=np.zeros((n,m))
    u[:,0]=A[:,0]
    q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(n):
            u[:,i]-=(A[:,i]@q[:,j]*q[:,j])
        q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    for i in range(n):
        for j in range(i,m):
            r[i,j]=A[:,j]@q[:,i]
    print(f"The Q Matrix is\n {q}")
    print(f"The R Matrix is\n {r}")
a=np.array(eval(input()))
QR_Decomposition(a)

```

## Output

<img width="1919" height="898" alt="Screenshot 2025-11-27 113146" src="https://github.com/user-attachments/assets/a3146ed0-5880-4e55-87d0-0c604c276b00" />




## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
