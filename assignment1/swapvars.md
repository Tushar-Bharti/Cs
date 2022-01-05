# assignment 1
## write a c program to swap the values of two variables.
### solution
```c
#include <stdio.h>

int main(void)
{
    int a, b;
    printf("Enter Value a:");
    scanf("%d", &a);
    printf("Enter Value b:");
    scanf("%d", &b);
    int c = a;
    a = b;
    b = c;

    printf("Swapped values! now value of a is %d and b is %d", a, b);
    return 0;
}
```
![image](https://user-images.githubusercontent.com/96988507/148280142-00607a83-b050-472c-ab72-2513066da1bf.png)

