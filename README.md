## EX. NO: 3  IMPLEMENTATION OF HILL CIPHER

### Name           : Swaminathan.V
### Register Number: 212223110057

## AIM:
  To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. 
Often the simple scheme A = 0, B= 1... Z = 25, is used, but this is not an essential feature of the cipher. 
To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. 
To decrypt the message, each block is multiplied by the inverse of the m trix used for encryption. 
The matrix used for encryption is the cipher key, and it should be chosen
 randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:
```
STEP-1: Read the plain text and key from the user. 
STEP-2: Split the plain text into groups of length three.
STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.
```

## PROGRAM :
```
#include <stdio.h>
#include <stdlib.h>
void caesarEncrypt(char *text, int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        char c = text[i];
        if (c >= 'A' && c <= 'Z') {
            text[i] = ((c - 'A' + key) % 26 + 26) % 26 + 'A';
        }
        else if (c >= 'a' && c <= 'z') {
            text[i] = ((c - 'a' + key) % 26 + 26) % 26 + 'a';
        }
    }
}

void caesarDecrypt(char *text, int key) {
    caesarEncrypt(text, -key);
}

int main() {
    char message[100];
    int key;

    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin);

    printf("Enter the Caesar Cipher key (an integer): ");
    scanf("%d", &key); 
    caesarEncrypt(message, key);
    printf("Encrypted Message: %s", message);

    caesarDecrypt(message, key);
    printf("Decrypted Message: %s", message);

    return 0;
}

```
## OUTPUT:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/22b8e695-cc03-4ab8-82cf-99c304548db2" />


## RESULT:
Thus the program executed successfully.

