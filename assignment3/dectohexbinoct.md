# Write a C program to accept the number in decimal and print the number in binary, octal  and hexadecimal.

## Solution
>```c
>#include <stdio.h>
>
>// function to print array in reverse order
>void printReverseArray(int *arr, int i)
>
>{
>    i -= 1;
>    while (i >= 0)
>    {
>        printf("%d", arr[i]);
>        i--;
>    }
>}
>void toBinary(int decimal)
>{
>    int arr[64];
>    int i = 0;
>    while (decimal > 0)
>    {
>        arr[i] = decimal % 2;
>        decimal = decimal / 2;
>        i++;
>    }
>    printReverseArray(arr, i);
>}
>
>void toOctal(int decimal)
>{
>    int arr[64];
>    int i = 0;
>    while (decimal > 0)
>    {
>        arr[i] = decimal % 8;
>        decimal = decimal / 8;
>        i++;
>    }
>
>    printReverseArray(arr, i);
>}
>
>void toHex(int decimal)
>{
>    int arr[64];
>    int i = 0;
>    while (decimal > 0)
>    {
>        arr[i] = decimal % 16;
>        decimal = decimal / 16;
>        i++;
>    }
>
>    printReverseArray(arr, i);
>}
>
>int main(void)
>{
>    int decimal;
>    printf("Enter a decimal ->");
>    scanf("%d", &decimal);
>
>    printf("Binary form of decimal %d is: ", decimal);
>    toBinary(decimal);
>
>    printf("\nOctal form of decimal %d is: ", decimal);
>    toOctal(decimal);
>
>    printf("\nHex form of decimal %d is: ", decimal);
>    toHex(decimal);
>    return 0;
>}
>```
## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151668930-2210d729-39e3-40ac-9e34-e52dbfcd58d1.png)
