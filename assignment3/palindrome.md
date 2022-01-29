# Write a C Program to enter a number (integer), reverse it and check it whether it is a  palindrome number or not.

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
>    printf("Reverse of %d is: %d\n", i, reversed);
>    return i == reversed;
>}
>
>int main(void)
>{
>    int i;
>    printf("Enter a number to check ->");
>    scanf("%d", &i);
>    int ans = PalindromeChecker(i);
>    printf(ans == 1 ? "Yes! Number %d is a palindrome number" : "No! Number %d is not a palindrome number", i);
>    return 0;
>}
>```
## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151669194-688546b8-d7a7-4252-8eb5-f57c8146c717.png)
