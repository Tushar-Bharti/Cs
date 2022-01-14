# Write a C program to print the default values of uninitialized variables of various  types.

## Solution:
>```c
>#include <stdio.h>
>
>int main(void) {
>    int a ;
>    float b;
>    char c ;
>    long d;
>    short e ;
>    double f ;
>    long long g ;
>    int *h ;
>    long double i;
>    short int j;
>
>    printf("These values can change for different runs and different ordering of printf\n\n\n");
>    printf("uninitialized int type -> %d\n",a);
>    printf("uninitialized float type -> %f\n", b);
>    printf("uninitialized char type -> %c\n", c);
>    printf("uninitialized long type -> %li\n", d);
>    printf("uninitialized short type -> %hi\n", e);
>    printf("uninitialized double type -> %lf\n", f);
>    printf("uninitialized long long type -> %lli\n", g);
>    printf("uninitialized int pointer type -> %p\n", h);
>    printf("uninitialized long double type -> %Lf\n", i);
>    printf("uninitialized short int type -> %hi\n", j);
>
>    return 0;
>}
>```
## Output
### different runs
>![image](https://user-images.githubusercontent.com/96988507/149585465-fa9b0546-45d9-49fe-9752-3764b5e2f679.png)
### different order
#### order 1
>![order 1](https://user-images.githubusercontent.com/96988507/149585692-7d0543f8-8b58-447b-806f-778f0c9de294.jpeg)
#### order 2
>![order 2](https://user-images.githubusercontent.com/96988507/149585695-a6dd844e-9671-4a36-9b2f-0da75152f4ce.jpeg)

##### note
> **this can also change for different platform and compiler**
