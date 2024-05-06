# Ex-2 IMPLEMENTATION-OF-SYMBOL-TABLE
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol is inserted into symbol table along with its memory address.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h>
#include <conio.h> 
#include <ctype.h> 
#include <stdlib.h>
#include <string.h> 
#include <math.h>

void main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    void *p, *add[5];
    char ch, srch, b[15], d[15], c;

    printf("Enter the Expression terminated by $:");
    while ((c = getchar()) != '$') {
        b[i] = c;
        i++;
    }
    n = i - 1;

    printf("Given Expression:");
    for (i = 0; i <= n; i++) {
        printf("%c", b[i]);
    }

    printf("\n Symbol Table\n");
    printf("Symbol\taddr\t\ttype");

    while (j <= n) {
        c = b[j];
        if (isalpha((unsigned char)c)) {
            if (j == n) {
                p = malloc(1);
                add[x] = p;
                d[x] = c;
                printf("%c\t%p\tidentifier", c, p);
            } else {
                ch = b[j + 1];
                if (ch == '+' || ch == '-' || ch == '*' || ch == '=') {
                    p = malloc(1);
                    add[x] = p;
                    d[x] = c;
                    printf("\n%c\t%p\tidentifier\n", c, p);
                    x++;
                }
            }
        }
        j++;
    }

    printf("\n The symbol is to be searched: ");
    srch = getch();
    for (i = 0; i <= x; i++) {
        if (srch == d[i]) {
            printf("\n Symbol Found");
            printf("\n%c%s%p\n", srch, "@address", add[i]);
            flag = 1;
        }
    }

    if (flag == 0)
        printf("\nSymbol Not Found");
}
```
# OUTPUT
![image](https://github.com/sharavanan2307/IMPLEMENTATION-OF-SYMBOL-TABLE-/assets/119393651/05684dac-25f0-4e00-92f8-6a101bd9a2f8)

# RESULT
### The program to implement a symbol table is executed and the output is verified.
