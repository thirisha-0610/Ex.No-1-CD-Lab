# Ex. No : 1

# IMPLEMENTATION OF SYMBOL TABLE

# Register Number :212223040228

# Date :25/08/25

# AIM:

To write a C program to implement a symbol table.

# ALGORITHM:

1. Start the program.
2. Get the input from the user with the terminating symbol ‘$’.
3. Allocate memory for the variable by dynamic memory allocation function.
4. If the next character of the symbol is an operator then only the memory is allocated.
5. While reading, the input symbol is inserted into symbol table along with its memory address.
6. The steps are repeated till ‘$’ is reached.
7. To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8. Stop the program.

# PROGRAM:
```
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <string.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    void *add[5];
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0';
    n = i - 1;

    printf("Given Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\taddr\ttype\n");

    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) {
            if (j == n) {
                void *p = malloc(sizeof(char));
                add[x] = p;
                d[x] = c;
                printf("%c\t%p\tidentifier\n", c, p);
            } else {
                char ch = b[j + 1];
                if (ch == '+' || ch == '-' || ch == '*' || ch == '=') {
                    void *p = malloc(sizeof(char));
                    add[x] = p;
                    d[x] = c;
                    printf("%c\t%p\tidentifier\n", c, p);
                    x++;
                }
            }
        }
    }

    printf("\nThe symbol to be searched: ");
    getchar();
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("%c@address%p\n", srch, add[i]);
            flag = 1;
        }
    }

    if (flag == 0)
        printf("Symbol Not Found\n");

    for (i = 0; i < x; i++) {
        free(add[i]);
    }

    return 0;
}
```

# OUTPUT:

<img width="558" height="498" alt="481478602-511adf41-7672-47ee-8772-94faf1107668" src="https://github.com/user-attachments/assets/f45a1819-aa35-4a62-8ff4-81e8c319ba26" />

<img width="543" height="514" alt="481478971-67e7332e-c311-421e-9b72-eee2675f9174" src="https://github.com/user-attachments/assets/c535d1d3-75af-4547-89ea-50b9d3effa35" />

# RESULT:

The program to implement a symbol table is executed and the output is verified.
