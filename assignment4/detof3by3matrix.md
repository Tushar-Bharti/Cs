# Write a C program to input a 3x3 matrix and find its determinant.  

## Solution
```c
#include <stdio.h>

int det(int arr[3][3])
{
    return (arr[0][0] * (arr[1][1] * arr[2][2] - arr[1][2] * arr[2][1]) -
            arr[0][1] * (arr[1][0] * arr[2][2] - arr[1][2] * arr[2][0]) +
            arr[0][2] * (arr[1][0] * arr[2][1] - arr[2][0] * arr[1][1]));
}

void printMatrix(int arr[3][3])
{

    int i = 0;
    while (i < 3)
    {
        printf("|%d %d %d|\n", arr[i][0], arr[i][1], arr[i][2]);
        i++;
    }
}

int main(void)
{
    int arr[3][3];
    printf("enter the elements of matrix (format : a11 a12 a13 a21 a22 a23 a31 a32 a33) ->");
    int j = 0;
    while (j < 3)
    {
        int k = 0;
        while (k < 3)
        {
            scanf("%d", &arr[j][k]);
            k++;
        }
        j++;
    }

    printf("Original Matrix:\n");
    printMatrix(arr);

    printf("determinant -> %d", det(arr));

    return 0;
}
```

## Screenshot
![image](https://user-images.githubusercontent.com/96988507/156174317-10935291-3fb0-4a5a-ba7b-8d66a19983d5.png)
