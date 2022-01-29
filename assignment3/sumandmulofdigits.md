# Write a C program to enter a number (integer), find the sum and product of its digits. 
## hint
>**INPUT: number=1234;**
>
> **OUTPUT: sum of digits=10 and product of digits= 24**

## Solution
>```c
>#include <stdio.h>
>int main(void)
>{
>
>    int i, sum = 0, mul = 1;
>    printf("Enter a number ->");
>    scanf("%d", &i);
>
>    int number = i;
>
>    while (i > 0)
>    {
>        int current = i % 10;
>        sum += current;
>        mul *= current;
>
>        i = i / 10;
>    }
>
>    printf("For the number %d ,Sum of its digits is %d and multiplication of its digits is %d ", number, sum, mul);
>
>    return 0;
>}
>```

## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151669104-5591208c-7974-4741-a8af-8b352e400776.png)
