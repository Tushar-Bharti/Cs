# Write a C program to find the palindrome numbers between 1 to 100.

## Solution
>```c
>#include <stdio.h>
>
>int PalindromeChecker(int i)
>{
>    int reversed = 0, number = i;
>    while (number > 0)
>    {
>        int r = number % 10;
>        reversed = reversed * 10 + r;
>        number /= 10;
>    }
>    return i == reversed;
>}
>
>int main(void)
>{
>    printf("Palindrome numbers between 0 and 100 are:");
>    int i = 1;
>    while (i < 100)
>    {
>        int isPalindrome = PalindromeChecker(i);
>        if (isPalindrome == 1)
>        {
>            printf("\n%d", i);
>        }
>        i++;
>    }
>    return 0;
>}
>```
## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151669518-f60ec573-6461-41da-b77a-e714e04e47ed.png)
