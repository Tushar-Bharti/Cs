# Write C programs to print the following pyramids (input value of n).  
## Structure (taking n = 5)
### A) Left Side Pyramid
```c
            1
         1  2
      1  2  3
   1  2  3  4
1  3  3  4  5
```
### B) Right Side Pyramid
```c
1
1  2
1  2  3
1  2  3  4
1  2  3  4  5
```
### C) Both Side Pyramid
```c
        1   
      2 1 2  
    3 2 1 2 3
  4 3 2 1 2 3 4 
5 4 3 2 1 2 3 4 5
```
## Solution
## Method 1: Using nested loop for each type
>```c
>#include <stdio.h>
>
>void RightSidePyramid(int height)
>{
>    int i = 0;
>    while (i < height)
>    {
>        int j = 1;
>        int arr[10000];
>        int u = 0;
>        while (j <= (i + 1))
>        {
>            printf("%d%s", j, "   ");
>            j++;
>        }
>        printf("\n");
>        i++;
>    }
>}
>
>void LeftSidePyramid(int height)
>{
>    int i = 0;
>    while (i < height)
>    {
>        int j = 1;
>        int u = 0;
>        while (u < (height - i))
>        {
>            printf("    ");
>            u++;
>        }
>        while (j <= (i + 1))
>        {
>            printf("%d%s", j, "   ");
>            j++;
>        }
>        printf("\n");
>        i++;
>    }
>}
>
>void BothSidePyramid(int height)
>{
>    int i = 0;
>    while (i < height)
>    {
>        int j = 1;
>        int u = 0;
>        while (u < (height - i))
>        {
>            printf("    ");
>            u++;
>        }
>        int rev = 0;
>        while (j <= (i + 1))
>        {
>            printf("%d%s", j, "   ");
>            if (j == (i + 1))
>                rev = 1;
>            j++;
>        }
>        if (rev == 1)
>        {
>            j -= 2;
>            while (j > 0)
>            {
>                printf("%d%s", j, "   ");
>                j--;
>            }
>        }
>        printf("\n");
>        i++;
>    }
>}
>
>int main(void)
>{
>    int height;
>    printf("Enter the height of pyramid ->");
>    scanf("%d", &height);
>
>    printf("Right Side Pyramid\n");
>    RightSidePyramid(height);
>
>    printf("\n\nLeft Side Pyramid\n");
>    LeftSidePyramid(height);
>
>    printf("\n\nBoth Side Pyramid\n");
>    BothSidePyramid(height);
>    return 0;
>}
>```
### Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151669851-06dd0495-1178-44fe-bcdf-33d8d277db66.png)

### Method 2: using snprintf
>```c
>#include <stdio.h>
>#include <stdlib.h>
>#include <string.h>
>
>const char *repeatIndent(int n)
>{
>    char res[10000];
>    char temp[10000];
>    strcpy(res, temp);
>    char indent[7] = "      ";
>    while (n > 0)
>    {
>        strcat(res, indent);
>        n--;
>    }
>    char *result = res;
>    return result;
>}
>
>void RightSidePyramid(int height)
>{
>    char indent[7] = "     ";
>    int i = 1;
>    char start[10000];
>    while (i <= height)
>    {
>        snprintf(start, sizeof(start), "%s%s%d", start, indent, i);
>
>        printf("%s\n", start);
>        i++;
>    }
>}
>
>void LeftSidePyramid(int height)
>{
>    char indent[7] = "     ";
>    int i = 1;
>    char start[10000] = "";
>    while (i <= height)
>    {
>        char prev[10000] = "";
>        strcpy(prev, start);
>        snprintf(start, sizeof(start), "%s%s%d", prev, indent, i);
>        int n = height - i;
>
>        printf("%s%s\n", repeatIndent(n), start);
>        i++;
>    }
>}
>
>void BothSidePyramid(int height)
>{
>    char indent[7] = "     ";
>    int i = 1;
>    char start[100000] = "1";
>    while (i <= height)
>    {
>        char prev[10000];
>        strcpy(prev, start);
>        if (i == 1)
>        {
>            printf("%s%s\n", repeatIndent(height - i), start);
>        }
>        else
>        {
>            snprintf(start, sizeof(start), "%d%s%s%s%d", i, indent, prev, indent, i);
>            printf("%s%s\n", repeatIndent(height - i), start);
>        }
>        i++;
>    }
>}
>int main(void)
>{
>    int height;
>    printf("Enter the height of pyramid ->");
>    scanf("%d", &height);
>
>    printf("Right Side Pyramid:\n");
>    RightSidePyramid(height);
>
>    printf("\n\nLeft Side Pyramid:\n");
>    LeftSidePyramid(height);
>
>    printf("\n\nBoth Side Pyramid:\n");
>    BothSidePyramid(height);
>    return 0;
>}
>```
### Screenshot
>![image](https://user-images.githubusercontent.com/96988507/151669905-c9808f2e-8aa9-4038-b71f-c465e6c2f54f.png)
