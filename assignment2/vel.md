# Write a C program to calculate velocity of a car when distance and time are given by  the user.

## Solution:
>```c
>#include <stdio.h>
>
>int main(void) {
>    float d,t;
>    printf("Enter the distance travelled by the car (in meter) ->");
>    scanf("%f",&d);
>    printf("Enter the time taken by the car (in seconds) ->");
>    scanf("%f", &t);
>
>    printf("Velocity of the car is %f m/s",d/t);
>    return 0;
>}
>```
## Output
![image](https://user-images.githubusercontent.com/96988507/149584628-3c448a98-32b9-42a9-96d3-2ce10f0a2522.png)

