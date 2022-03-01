# Write a C program to perform the matrix multiplication. Assume that the input matrices  are compatible for multiplication.  

## Solution
```c
#include <stdio.h>

void printMatrix(int arr[10][10], int r, int c)
{
    int i = 0;
    while (i < r)
    {
        int j = 0;
        printf("|");
        while (j < c)
        {
            printf(" %d", arr[i][j]);
            j++;
        }
        printf("|\n");
        i++;
    }
}

void mulmatrix(int matrixone[10][10], int matrixtwo[10][10], int mc, int mr, int mtc, int mtr)
{
    int matrix[10][10];
    if (mr != mtc)
    {
        printf("Matrix cant be multiplied");
    }
    else
    {

        int i = 0;
        while(i < mr) {
            int j =0;
            while(j < mtc){
                matrix[i][j] = 0;
                j++;
            }
            i++;
        }
        i = 0;
        while (i < mr)
        {
            int j = 0;
            while (j < mtc)
            {
                matrix[i][j] = 0;
                int k = 0;
                while (k < mtr)
                {
                    matrix[i][j] += matrixone[i][k] * matrixtwo[k][j];
                    //printf("matrix[%d,%d] -> %d\n", i, j, matrix[i][j]);
                    k++;
                }
                j++;
            }
            i++;
        }
        printMatrix(matrix,mr,mtc);
    }
}
int main(void)
{
    int matrixone[10][10];
    int matrixtwo[10][10];
    int mc, mr, mtc, mtr;
    printf("enter the length of rows of matrix ->");
    scanf("%d", &mr);
    printf("enter the length of columns of matrix ->");
    scanf("%d", &mc);

    int i = 0;
    printf("Enter the elements of matrix (format : a11 a12 ... a1i a21 a22 ... a2i ... aj1 ... aji) -> ");
    while (i < mr)
    {
        int j = 0;
        while (j < mc)
        {
            scanf("%d", &matrixone[i][j]);
            j++;
        }
        i++;
    }

    printf("Matrix One:\n");
    printMatrix(matrixone, mr, mc);

    printf("enter the length of rows of matrix ->");
    scanf("%d", &mtr);
    printf("enter the length of columns of matrix ->");
    scanf("%d", &mtc);

    i = 0;
    printf("Enter the elements of matrix (format : a11 a12 ... a1i a21 a22 ... a2i ... aj1 ... aji) -> ");
    while (i < mtr)
    {
        int j = 0;
        while (j < mtc)
        {
            scanf("%d", &matrixtwo[i][j]);
            j++;
        }
        i++;
    }
    printf("Matrix Two:\n");
    printMatrix(matrixtwo, mtr, mtc);

    printf("multiplication of matrices is:\n");
    mulmatrix(matrixone,matrixtwo,mc,mr,mtc,mtr);

    return 0;
}
```

## Screenshot
![image](https://user-images.githubusercontent.com/96988507/156175980-2c028ce2-4c7f-4c1d-8dcb-16fca07927ec.png)
![image](https://user-images.githubusercontent.com/96988507/156175994-67dfeab5-f620-4a45-83fd-9a8552db766e.png)
