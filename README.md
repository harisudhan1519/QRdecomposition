Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:



## Program:
### Gram-Schmidt Method
```
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:, 0]=A[:, 0]
    Q[:, 0]=u[:, 0] / np.linalg.norm(u[:, 0])
    for i in range(1, n):
        u[:, i]=A[:, i]
        for j in range(i):
            u[:, i]-=(A[:, i] @ Q[:, j] * Q[:, j])
        Q[:, i]=u[:, i] / np.linalg.norm(u[:, i])
    R=np.zeros((n, m))
    for i in range(n):
        for j in range(i, m):
            R[i, j]=A[:, j] @ Q[:, i]
    print("The Q Matrix is")
    print(f" {Q}")
    print("The R Matrix is")
    print(f" {R}")
a = np.array(eval(input()))
QR_Decomposition(a)


```

## Output

![image](https://github.com/user-attachments/assets/55450e39-8d10-4f8a-8d61-3f6a11235856)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
