# Write a C program input “n” number of elements into an array and perform the following  operations using calling functions (pass the array into the called function).  

## Operations
i. Find the smallest number (the function must return the smallest number) 
ii. Find the largest number (the function must return the largest number) 
iii. Search a given number in the array (the function must return the status of search  (success of not success) 

## Solution
```c
#include <stdio.h>

int smallestInArray(int *arr, int n)
{
    int small;
    int i = n;
    while (n--)
    {
        if (i == n)
        {
            small = arr[n];
        }
        else
        {
            if (arr[n] < small)
            {
                small = arr[n];
            }
        }
    }

    return small;
}
int largestInArray(int *arr, int n)
{
    int large;
    int i = n;
    while (n--)
    {
        if (i == n)
        {
            large = arr[n];
        }
        else
        {
            if (arr[n] > large)
            {
                large = arr[n];
            }
        }
    }

    return large;
}

void find(int *arr, int n, int number)
{
    int found = 1;
    while (n--)
    {
        if (arr[n] == number)
        {
            found = 0;
            break;
        }
    }

    printf(found == 0 ? "success" : "not success");
}

int main(void)
{
    int n;
    int i = 0;
    int num;
    int arr[100000];
    printf("enter the length of array ->");
    scanf("%d", &n);

    printf("\nenter the n elements of array ->");
    while (i < n)
    {
        scanf("%d", &arr[i]);
        i++;
    }

    printf("\n smallest number is -> %d\n", smallestInArray(arr, n));
    printf("\n largest number is -> %d\n", largestInArray(arr, n));
    printf("enter a number to find in array ->");
    scanf("%d", &num);
    find(arr, n, num);

    return 0;
}

```

## Screenshot
![image](https://user-images.githubusercontent.com/96988507/156174038-1cabb25c-6f13-4253-9913-610ffecf9c0e.png)

