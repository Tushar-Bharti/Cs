# Write a C program which takes temperature in Celsius and convert that into Fahrenheit.

## Solution
>```c
>#include <stdio.h>
>int main(void)
>{
>    float c;
>    printf("Enter the temperature in (Celsius) ->");
>    scanf("%f", &c);
>
>    float f = (((9 * c) / 5) + 32);
>
>    printf("Converted %.2f Celsius to %.2f Fahrenheit", c, f);
>    return 0;
>}
>```
## Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151668743-a66c0992-fb72-408a-a748-776271403ecf.png)
