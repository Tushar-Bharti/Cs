# Write a C program to input “n” numbers into an array and check for each element of the  array whether it is a prime or not. Computation of checking primary should be done using  a function call.

## Solution
```c
#include <stdio.h>
#include <math.h>

int isPrime(int num)
{
    int ans = 1;
    if(num == 2 || num == 3) return 0;
    int half = sqrt(num);
    int i = 2;
    while (i <= half)
    {
        if (num % i != 0)
        {
            ans = 0;
            break;
        }
        i++;
    }
    return ans;
}

int main(void)
{
    int n;
    int i = 0;
    int arr[100000];
    printf("enter the length of array ->");
    scanf("%d", &n);

    printf("\nenter the n elements of array ->");
    while (i < n)
    {
        scanf("%d", &arr[i]);
        i++;
    }
    i = 0;
    while (i < n)
    {
        if (isPrime(arr[i]) == 0)
        {
            printf("%d is prime\n", arr[i]);
        }
        else
        {
            printf("%d is not prime\n", arr[i]);
        }
        i++;
    }
    return 0;
}
```

## Screenshot

![image](https://user-images.githubusercontent.com/96988507/156177423-41c5ba3e-d6f7-41f4-80e7-80e21fab58aa.png)
