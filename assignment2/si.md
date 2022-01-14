# Write a C program to calculate simple interest where the principal amount, time and rate are  provided by the user.

## Solution:
>```c
>#include <stdio.h>
>
>int main(void) {
>    int p,r,t;
>    printf("Enter Principal ->");
>    scanf("%d",&p);
>    printf("Enter Rate of interest in (%%) ->");
>    scanf("%d", &r);
>    printf("Enter Time (in year) ->");
>    scanf("%d", &t);
>
>    printf("Simple Interest is -> %f", (float)((p*r*t)/100));
>    return 0;
>}
>```
## Output
>![image](https://user-images.githubusercontent.com/96988507/149585090-3c416eea-c1d4-4c34-aecb-adce7a43ad13.png)
