# Write a C program to find the sum of the series up to n (give as input) terms. 
## Series 
> **1+2+4+7+11+16+22+……………………… (up to n terms)**
## Solution
>```c
>#include <stdio.h>
>
>int main(void)
>{
>    int start = 1, sum = 0, diff = 1, n;
>    printf("Enter the Limit of the Series (n) ->");
>    scanf("%d", &n);
>
>    int u = 0;
>    while (u < n)
>    {
>        sum += start;
>        start += diff;
>        diff += 1;
>        u++;
>    }
>
>    printf("Sum of the series with endlimit n (%d) is %d", n, sum);
>    return 0;
>}
>```

## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151670144-1e24cb70-2f90-48af-92af-c8134c6a1511.png)
