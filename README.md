# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char plain[100], cipher[100];
    int key, i, length;

    printf("Enter the plain text: ");
    scanf("%99s", plain);

    printf("Enter the key value: ");
    scanf("%d", &key);

    key = ((key % 26) + 26) % 26;
    length = strlen(plain);

    printf("\nPLAIN TEXT: %s", plain);

    for (i = 0; i < length; i++)
    {
        if (isupper((unsigned char)plain[i]))
            cipher[i] = (plain[i] - 'A' + key) % 26 + 'A';
        else if (islower((unsigned char)plain[i]))
            cipher[i] = (plain[i] - 'a' + key) % 26 + 'a';
        else
            cipher[i] = plain[i];
    }

    cipher[length] = '\0';

    printf("\n\nENCRYPTED TEXT: %s", cipher);

    for (i = 0; i < length; i++)
    {
        if (isupper((unsigned char)cipher[i]))
            plain[i] = (cipher[i] - 'A' - key + 26) % 26 + 'A';
        else if (islower((unsigned char)cipher[i]))
            plain[i] = (cipher[i] - 'a' - key + 26) % 26 + 'a';
        else
            plain[i] = cipher[i];
    }

    plain[length] = '\0';

    printf("\n\nAFTER DECRYPTION: %s\n", plain);

    return 0;
}
```

## OUTPUT:
<img width="1892" height="977" alt="image" src="https://github.com/user-attachments/assets/4d0cb8de-729d-4f28-af50-a1147044c5c3" />


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
