# Input a number and a digit and find whether the digit is present in the number or not, if  present then count the number of times it occurs in the number.

## Solution
>```c
>#include <stdio.h>
>
>int main(void)
>{
>    int i, digit, times = 0, number;
>    printf("Enter a number ->");
>    scanf("%d", &i);
>
>    number = i;
>
>    printf("Enter a digit to check ->");
>    scanf("%d", &digit);
>
>    while (i > 0)
>    {
>        int current = i % 10;
>        if (current == digit)
>            times += 1;
>
>        i /= 10;
>    }
>
>    if (times == 0)
>    {
>        printf("The digit %d didn't appear any time in the number %d", digit, number);
>    }
>    else
>    {
>        printf("The digit %d appearred %d time in the number %d", digit, times, number);
>    }
>    return 0;
>}
>```
## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151670060-8a7bfd17-9756-457e-beee-9957225564a0.png)
