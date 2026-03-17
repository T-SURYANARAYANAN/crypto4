# VIGENERE-CIPHER
## EX. NO: 4
 

## IMPLEMETATION OF VIGENERE CIPHER
 

## AIM:

To implement the Vigenere Cipher substitution technique using C program.

## DESCRIPTION:

To encrypt, a table of alphabets can be used, termed a tabula recta, Vigenère square,or Vigenère table. It consists of the alphabet written out 26 times in differnt rows, each
 
alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses adifferent alphabet from one of the rows. The alphabet used at each point repeating keyword.depends on a Each row starts with a key letter. The remainder of the row holds the letters A to Z. Although there are 26 key rows shown, you will only use as many keys as there are unique letters in the key string, here just 5 keys, {L, E, M, O, N}. For successive letters of the message, we are going to take successive letters of the key string, and encipher each message letter using its corresponding key row. Choose the next letter of the key, go along that row to find the column heading that	atches the message character; the letter at the intersection of
[key-row, msg-col] is the enciphered letter.


## ALGORITHM:

STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.<br>
STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.<br>
STEP-3: Repeat this process for all 26 rows and construct the final key matrix.<br>
STEP-4: The keyword and the plain text is read from the user.<br>
STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.<br>
STEP-6: Pick the first letter of the plain text and that of the keyword as the row indices and column indices respectively.<br>
STEP-7: The junction character where these two meet forms the cipher character.<br>
STEP-8: Repeat the above steps to generate the entire cipher text.<br>


## PROGRAM
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100], key[100];
    int i, len, keyLen;

    printf("Enter text (UPPERCASE): ");
    scanf("%s", text);

    printf("Enter key (UPPERCASE): ");
    scanf("%s", key);

    len = strlen(text);
    keyLen = strlen(key);

    // Encryption
    for(i = 0; i < len; i++)
    {
        int shift = key[i % keyLen] - 'A';
        text[i] = 'A' + (text[i] - 'A' + shift) % 26;
    }

    printf("Encrypted Message: %s\n", text);

    // Decryption
    for(i = 0; i < len; i++)
    {
        int shift = key[i % keyLen] - 'A';
        text[i] = 'A' + (text[i] - 'A' + (26 - shift)) % 26;
    }

    printf("Decrypted Message: %s\n", text);

    return 0;
}
```
## OUTPUT
<img width="1303" height="673" alt="image" src="https://github.com/user-attachments/assets/c3f6d679-1992-4208-b6e3-7e36d00c98a9" />

## RESULT
Thus the implementation of VIGENERE CIPHER had been executed successfully.
