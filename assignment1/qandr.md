# assignment 1
## write a c program to find quotient and remainder.
### solution
```c
#include <stdio.h>

int quotient(int a, int b)
{
    int q = a / b;
    return q;
};

int remain(int a, int b)
{
    return a % b;
};

int main(void)
{
    int a, b;
    printf("Enter Number a:");
    scanf("%d", &a);

    printf("Enter Number b:");
    scanf("%d", &b);

    printf("Quotient is %d and Remainder is %d", quotient(a, b), remain(a, b));
    return 0;
}
```
![image](https://user-images.githubusercontent.com/96988507/148279395-38bfc820-4419-41d3-8477-cd0e044c9f0f.png)
