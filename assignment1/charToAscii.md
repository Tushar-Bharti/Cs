# assignment 1
## write a c program to represent english character with their ASCII values .
### solution
```c
#include <stdio.h>

int main(void) {
    char letter;
    printf("Enter a letter to get ASCII value of:");
    scanf("%c",&letter);

    printf("ASCII value of %c is %d",letter,letter);
    return 0;
}
```
![image](https://user-images.githubusercontent.com/96988507/148278358-1cac18a9-2a0d-49d0-80d1-5e0558b6a230.png)
