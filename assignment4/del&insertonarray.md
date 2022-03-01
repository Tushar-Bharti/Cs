# Write a C program to enter “n” integers into an array  perform a sequence of insertion (concept of Q2) and deletion (concept of Q1) operations  based on your input choice. It is assumed that after each operation the content of the array  should be updated. Further, you must check the two conditions. These are (i) if array is  empty and next operation is deletion, then it must display the message as “UNDER  FLOW”, and (ii) if array if full and next operation is insertion, then it must display the  message as “OVER FLOW”.

## Solution
```c
#include <stdio.h>
#include <string.h>

void printArray(int **arr, int size)
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
    int n, i = 0, *arr[100000];
    printf("Enter the length of array(n) -> ");
    scanf("%d", &n);

    printf("\n now enter n integers for the array -> ");

    while (i < n)
    {
        scanf("%d", &arr[i]);
        i++;
    }
    printArray(arr, n);

    char type[10];
    int m = n;
    while (strcmp(type, "end") != 0)
    {
        printf("\nEnter the type of sequence to be performed on array (type: ins | del | end)->");
        scanf("%s", &type);
        if (strcmp(type, "end") == 0)
        {
            printf("Ended The Sequence!");
            break;
        }
        else if (strcmp(type, "del") == 0)
        {
            if( m == 0) {
                printf("UNDER_FLOW");
                continue;
            }
            int *num;
            printf("Enter the number to removed from array ->");
            scanf("%d", &num);

            int a = 0, b = 0;
            while (a < m)
            {
                if (arr[a] == num)
                {
                    a++;
                }
                else
                {
                    arr[b] = arr[a];
                    a++;
                    b++;
                }
            }
            m = b;

            printf("new Array:\n");
            printArray(arr, m);
        }
        else if (strcmp(type, "ins") == 0) {
            if(m >= n) {
                printf("OVER_FLOW\n");
                continue;
            }
            int a = 0, b = 0;
            int *num,position;
            printf("Enter the number to be inserted in  array ->");
            scanf("%d",&num);
            printf("Enter the position where the number %d needs to be added -> (first element is at 0th position) ->",num);
            scanf("%d",&position);
    int *temp;
    int *tempnext;
    m += 1;
            while (a < m)
            {
               if(a < position) {
                   
               }
               else if(a == position) {
                   temp = arr[a];
                   arr[a] = num;
               }
               else {
                   tempnext = arr[a];
                   arr[a] = temp;
                   temp = tempnext;
               }
               a++;
            }
        printf("\nNew Array:\n");
        printArray(arr,m);
        }
        else {
            printf("Invalid Sequence Type provided");
            continue;
        }
    }

    return 0;
}
```
## ScreenShot
![image](https://user-images.githubusercontent.com/96988507/156171949-e6f0ddb1-255d-4649-b2f3-63ce88b3c337.png)
![image](https://user-images.githubusercontent.com/96988507/156171963-2ebe1910-cb42-4ac2-a136-82cf444810c5.png)

