#  Write a C program to find out whether a 2-dimension matrix is Symmetric or not. A matrix  is said to be a Symmetric matrix if transpose of the matrix is equal to the original matrix. 

## Solution:
```c
#include <stdio.h>

int main(void)
{
    int a11, a12, a21, a22;
    printf("enter a 2x2 matrix (format: a11 a12 a21 a22) -> ");
        scanf("%d", &a11);
        scanf("%d", &a12);
        scanf("%d", &a21);
        scanf("%d", &a22);
    
    if(a11 == a22 && a12 == a21) {
        printf("\n |%d  %d|\n |%d  %d|\n is symmetric",a11,a12,a21,a22);
    }
    else {
        printf("\n |%d  %d|\n |%d  %d|\n is not symmetric", a11, a12, a21, a22);
    }
    return 0;
}
```

## Screenshot
![image](https://user-images.githubusercontent.com/96988507/156172220-e562cb2e-3fa7-4fd3-bdbc-a1f54c6672c0.png)
