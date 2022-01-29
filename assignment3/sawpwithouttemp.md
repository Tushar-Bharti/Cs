# Write a C program to exchange the values of two variables without using third variable.
## Solution
>```c
>#include <stdio.h>
>
>int main(void)
>{
>    int a, b;
>    printf("Enter Number a ->");
>    scanf("%d", &a);
>
>    printf("Enter Number b ->");
>    scanf("%d", &b);
>
>    a = a * b;
>    b = a / b;
>    a = a / b;
>
>    printf("Values Swapped! Now value of a is %d and b is %d", a, b);
>
>    return 0;
>}
>```

## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151669011-6bc320cd-515d-465a-804f-ab7f5dc2994c.png)
