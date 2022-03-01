#  Write a C program to enter “n” integers into an array and insert a number in a particular  position (<=n) of the array and updated the content of the array.  

## hint
For Example, if array A= {1,3,2,3,4,5} and we want to insert a number -30 at 3rd position,  then the updated array will be A= {1,3,-30,2,,3,4,5} after deletion operation is completed.  Assume array[0] is the first position element of the array. 

## Solution
```c
#include <stdio.h>

void printArray(int *arr, int size)
{
    int i = 0;

    printf("Array [");
    while (i < size)
    {
        printf("%d", arr[i]);
        if (i < size - 1)
        {
            printf(", ");
        }
        i++;
    }
    printf("]");
}

int main(void)
{
    int n, num, position, i = 0, res[100000], arr[100000], u = 0;
    printf("Enter the length of array(n) -> ");
    scanf("%d", &n);

    printf("\n now enter n integers for the array -> ");

    while (i < n)
    {
        scanf("%d", &arr[i]);
        i++;
    }

    printf("\n now enter the number that needs to be inserted in array ->");
    scanf("%d", &num);

    printf("\n now enter the position where u want to add this number ->");
    scanf("%d", &position);

    i = 0;
    while (u < n + 1)
    {
        if (u == position - 1)
        {
            res[u] = num;
            u += 1;
        }
        else
        {
            res[u] = arr[i];
            i += 1;
            u += 1;
        }
    }

    printf("\n resultant array is:\n");
    printArray(res, u);

    return 0;
}
```
## ScreenShot
![image](https://user-images.githubusercontent.com/96988507/156171705-83ff5998-8b28-4d41-9a0d-e4d717f800d1.png)
