# Write a C program to enter “n” integers into an array and delete every occurrence of a given  number in that array and also update the contents of the array.  

## hint
For Example, if array A={1,3,2,3,4,5} and we want to delete every occurrence of number  3, then the updated array will be A={1,2,4,5} after deletion operation is completed.  
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
    int n, num, i = 0, res[100000], arr[100000], u = 0;
    printf("Enter the length of array(n) -> ");
    scanf("%d", &n);

    printf("\n now enter n integers for the array -> ");

    while (i < n)
    {
        scanf("%d", &arr[i]);
        i++;
    }

    printf("\n now enter the number that needs to be deleted from array ->");
    scanf("%d", &num);
    i = 0;
    while (i < n)
    {
        if (arr[i] == num)
        {
            i += 1;
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
## Sreenshot
![image](https://user-images.githubusercontent.com/96988507/156171252-7a960fa2-c236-4c44-8f86-6ccb1cab2a89.png)
