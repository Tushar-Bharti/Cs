# Write a C program to accept any four digited number and print that number in words. 
## Solution
>```c
>#include <stdio.h>
>
>void digitToWord(int a)
>{
>    if (a == 1)
>        printf("one");
>    else if (a == 2)
>        printf("two");
>    else if (a == 3)
>        printf("three");
>    else if (a == 4)
>        printf("four");
>    else if (a == 5)
>        printf("five");
>    else if (a == 6)
>        printf("six");
>    else if (a == 7)
>        printf("seven");
>    else if (a == 8)
>        printf("eight");
>    else if (a == 9)
>        printf("nine");
>}
>
>void tenthPlace(int a, int b)
>{
>    //if tenth place has value 1 else check for other numbers
>    if (a == 1)
>    {
>        //brute forcing all possible numbers from 10 to 19
>        if (b == 0)
>            printf("and ten");
>        else if (b == 1)
>            printf("and eleven");
>        else if (b == 2)
>            printf("and twelve");
>        else if (b == 3)
>            printf("and thirteen");
>        else if (b == 4)
>            printf("and fourteen");
>        else if (b == 5)
>            printf("and fifteen");
>        else if (b == 6)
>            printf("and sixteen");
>        else if (b == 7)
>            printf("and seventeen");
>        else if (b == 8)
>            printf("and eighteen");
>        else if (b == 9)
>            printf("and nineteen");
>    }
>    else if (a == 2)
>    {
>        printf("and twenty");
>    }
>    else if (a == 3)
>    {
>        printf("and thirty");
>    }
>    else if (a == 4)
>    {
>        printf("and fourty");
>    }
>    else if (a == 5)
>    {
>        printf("and fifty");
>    }
>    else if (a == 6)
>    {
>        printf("and sixty");
>    }
>    else if (a == 7)
>    {
>        printf("and seventy");
>    }
>    else if (a == 8)
>    {
>        printf("and eighty");
>    }
>    else if (a == 9)
>    {
>        printf("and ninety");
>    }
>}
>
>void numberToWord(int *arr)
>{
>    //checking for thousand place
>    if (arr[3] != 0)
>    {
>        digitToWord(arr[3]);
>        printf(" thousand ");
>    }
>    //checking for hundred place
>    if (arr[2] != 0)
>    {
>        digitToWord(arr[2]);
>        printf(" hundred ");
>    }
>    //checking for tens place
>    if (arr[1] != 0)
>    {
>        if (arr[1] == 1)
>        {
>            tenthPlace(arr[1], arr[0]);
>        }
>        else
>        {
>            tenthPlace(arr[1], arr[0]);
>            printf(" ");
>            digitToWord(arr[0]);
>        }
>    }
>    //if tens place is 0 but unit place is not 0
>    if (arr[1] == 0 && arr[0] != 0)
>    {
>        printf(" and ");
>        digitToWord(arr[0]);
>    }
>}
>
>int main(void)
>{
>    int i, num;
>    printf("Enter a Four Digit Number ->");
>    scanf("%d", &i);
>    num = i;
>    int arr[4];
>    int size = 0;
>    //storing each digit in an array
>    while (size < 4 && i > 0)
>    {
>        int current = i % 10;
>        arr[size] = current;
>        i /= 10;
>        size++;
>    }
>// if size is not 4 or i is not 0 ,print error message else print the answer
>    if (i != 0 || size != 4)
>    {
>        printf("Number is not a 4 digit number");
>    }
>    else
>    {
>        printf("The word form of %d is: ", num);
>        numberToWord(arr);
>    }
>    return 0;
>}
>```
## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151670207-06ad2bf4-8558-4a7f-beb3-81c36904ecd4.png)
