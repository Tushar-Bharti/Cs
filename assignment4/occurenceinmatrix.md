# Write a C program to count the occurrence of an element in the 2-dimenssional matrix  using function. Pass the matrix and number to the called function and perform computation  in the called function.

## Solution
```c
#include <stdio.h>

int occurenceInMatrix(int arr[2][2], int num)
{
    int count = 0;
    int i = 0;
    while (i < 2)
    {
        int j = 0;
        while (j < 2)
        {
            if (arr[i][j] == num)
                count++;
            j++;
        }
        i++;
    }
    return count;
}

void printMatrix(int arr[2][2])
{

    int i = 0;
    while (i < 2)
    {
        printf("|%d %d|\n", arr[i][0], arr[i][1]);
        i++;
    }
}

int main(void)
{
    int arr[2][2];
    int i = 0;
    printf("enter the elements of matrix (format : a11 a12 a21 a22) ->");
    while (i < 2)
    {
        int j = 0;
        while (j < 2)
        {
            scanf("%d", &arr[i][j]);
            j++;
        }
        i++;
    }

    printf("Original Matrix:\n");
    printMatrix(arr);

    printf("enter the number to count occurence in matrix ->");
    int num;
    scanf("%d", &num);

    printf("\n occurence of number %d in matrix is -> %d", num, occurenceInMatrix(arr, num));

    return 0;
}
```

## Screenshot
![image](https://user-images.githubusercontent.com/96988507/156174548-c147062b-187c-43bd-b6cd-5a1f8e1c7337.png)
