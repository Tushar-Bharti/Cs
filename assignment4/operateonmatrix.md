# Write a C program to input a 2-dimension matrix and perform the following operations.  

## Operations
i) Reverse the elements of each row of the matrix  
ii) Reverse the elements of each column of the matrix

## Solution
```c
#include <stdio.h>

void swapColumns(int a11, int a12, int a21, int a22)
{
    int temp;
    temp = a11;
    a11 = a12;
    a12 = temp;

    temp = a21;
    a21 = a22;
    a22 = temp;

    printf("\n |%d  %d|\n |%d  %d|\n", a11, a12, a21, a22);
}

void swapRows(int a11, int a12, int a21, int a22)
{
    int temp;
    temp = a11;
    a11 = a21;
    a21 = temp;

    temp = a12;
    a12 = a22;
    a22 = temp;

    printf("\n |%d  %d|\n |%d  %d|\n", a11, a12, a21, a22);
}

int main(void)
{
    int a11, a12, a21, a22, a, b, c, d;
    printf("enter a 2x2 matrix (format: a11 a12 a21 a22) -> ");
    scanf("%d", &a11);
    scanf("%d", &a12);
    scanf("%d", &a21);
    scanf("%d", &a22);
    printf("original matrix:");
    printf("\n |%d  %d|\n |%d  %d|\n", a11, a12, a21, a22);

    printf("swapped rows. the new matrix is:");
    swapRows(a11, a12, a21, a22);

    printf("swapped columns. the new matrix is:");
    swapColumns(a11, a12, a21, a22);

    return 0;
}
```

## Screenshot
![image](https://user-images.githubusercontent.com/96988507/156173792-8b996b46-52e3-4464-aaa2-c7f551545de6.png)
