# Ex-4 Rail-Fence-Program
## NAME : VARUN JC
## REG NO : 212224240179
# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.

STEP-2: Arrange the plain text in row columnar matrix format.

STEP-3: Now read the keyword depending on the number of columns of the plain text


STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.


STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```C
#include <stdio.h>
#include <string.h>

int main() {
    char text[100], rail[10][100];
    int i, j, k = 0, len, key;

    printf("Enter the plaintext: ");
    scanf("%s", text);

    printf("Enter the key (number of rows): ");
    scanf("%d", &key);

    len = strlen(text);

    for (i = 0; i < key; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = '\n';

    for (i = 0; i < len; i++)
        rail[i % key][i] = text[i];

    printf("Encrypted text: ");

    for (i = 0; i < key; i++)
        for (j = 0; j < len; j++)
            if (rail[i][j] != '\n')
                printf("%c", rail[i][j]);

    printf("\n");
    return 0;
}
```
# OUTPUT
<img width="1451" height="897" alt="image" src="https://github.com/user-attachments/assets/af606ade-979f-4b92-9f7f-c3426e5a291d" />

# RESULT
Thus, the Rail fence transposition technique has been implemented and excecuted Successfully.

