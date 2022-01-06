# Assignment 1 
## create a c program to do addition , subtraction , multiplication and division

### solution
#### 1) doing all operations on same input
```c
#include <stdio.h>
int main(void)
{
    int a, b;
    printf("Enter Number a:");
    scanf("%d", &a);
    printf("Enter Number b:");
    scanf("%d", &b);

    printf("Answer to this is: \nAddition: %d \n Subtaction: %d \n Multiplication: %d\n Division: %d", a + b, a - b, a * b, a / b);
    return 0;
}

```
![2022-01-06 (13)](https://user-images.githubusercontent.com/96988507/148384891-dc2b6b34-44df-4099-8af2-e8d8c319d081.png)

#### 2) selecting an operation and then do operation on provided input
```c
#include <stdio.h>
#include <string.h>

int add(int a, int b)
{
    return a + b;
}
int sub(int a, int b)
{
    return a - b;
}
int mul(int a, int b)
{
    return a * b;
}
int div(int a, int b)
{
    return a / b;
}
int main(void)
{
    char type[4];
    printf("What operation do you want to select (add,sub,mul,div)\n");
    scanf("%s", type);

    if (strcmp(type, "add") == 0)
    {
        printf("Addition is chosen.now\n");
        int a, b;
        printf("Enter Number a:");
        scanf("%d", &a);
        printf("Enter Number b:");
        scanf("%d", &b);
        printf("Answer is:%d", add(a, b));
    }
    else if (strcmp(type, "sub") == 0)
    {
        printf("Subtraction is chosen.now\n");
        int a, b;
        printf("Enter Number a:");
        scanf("%d", &a);
        printf("Enter Number b:");
        scanf("%d", &b);
        printf("Answer is:%d", sub(a, b));
    }
    else if (strcmp(type, "mul") == 0)
    {
        printf("Multiplication is chosen.now\n");
        int a, b;
        printf("Enter Number a:");
        scanf("%d", &a);
        printf("Enter Number b:");
        scanf("%d", &b);
        printf("Answer is:%d", mul(a, b));
    }
    else if (strcmp(type, "div") == 0)
    {
        printf("Division is chosen.now\n");
        int a, b;
        printf("Enter Number a:");
        scanf("%d", &a);
        printf("Enter Number b:");
        scanf("%d", &b);
        printf("Answer is:%d", div(a, b));
    }
    else
    {
        printf("Invalid Type provided!");
    }
    return 0;
}
```

![Solution for screenshot](https://user-images.githubusercontent.com/96988507/148276996-77afa040-58d2-4a02-8390-d728671fcc65.png)

