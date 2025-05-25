## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
## Submitted By: Saravanan G
## Reference Number:212223230194

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

## Step 1: Choose a Key
● The key is a number (e.g., 3), which determines how many positions each
letter in the message will be shifted.<br>
● For example, if the key is 3, "A" becomes "D", "B" becomes "E", and so on.
## Step 2: Prepare the Message
● Take the message (plaintext) you want to encrypt.<br>
● The message should be in uppercase or lowercase letters. Spaces,
punctuation, and numbers can be left as is, or you may choose to remove
them.
## Step 3: Shift Each Letter
● For each letter in the message:
○ Convert the letter to its corresponding position in the alphabet (e.g., A =
0, B = 1, ..., Z = 25).<br>
○ Shift the letter forward by the key value (e.g., if the key is 3, add 3 to
the letter's position).<br>
○ If the letter exceeds 'Z' or 'z', wrap around to the start of the alphabet.
## Step 4: Convert Back to Letters
● After shifting, convert the new positions back to letters.<br>
○ If the shift is positive, the letter will advance forward in the alphabet.<br>
○ If the shift is negative (for decryption), the letter will move backward in
the alphabet.
## Step 5: Combine the Result
● After all the letters have been shifted and converted back to characters,
combine them to form the final ciphertext (encrypted message).<br>
● If decryption is needed, reverse the process by shifting each letter backward
by the key

## PROGRAM :-
```
#include <stdio.h>
#include <string.h>
void encrypt(char *text, int key) {
 int i;
 for (i = 0; text[i] != '\0'; i++) {
 if (text[i] >= 'A' && text[i] <= 'Z') {
 text[i] = (text[i] - 'A' + key) % 26 + 'A';
 }
 else if (text[i] >= 'a' && text[i] <= 'z') {
 text[i] = (text[i] - 'a' + key) % 26 + 'a';
 }
 }
}
void decrypt(char *text, int key) {
 int i;
 for (i = 0; text[i] != '\0'; i++) {
 if (text[i] >= 'A' && text[i] <= 'Z') {
 text[i] = (text[i] - 'A' - key + 26) % 26 + 'A';
 }
 else if (text[i] >= 'a' && text[i] <= 'z') {
 text[i] = (text[i] - 'a' - key + 26) % 26 + 'a';
 }
 }
}
int main() {
 char text[100];
 int key;
 printf("Enter text to be encrypted: ");
 scanf("%[^\n]", text);
 printf("Enter key (shift value): ");
 scanf("%d", &key);
 encrypt(text, key);
 printf("Encrypted text: %s\n", text);
 decrypt(text, key);
 printf("Decrypted text: %s\n", text);
 ret
```


## OUTPUT :-
 ![image](https://github.com/user-attachments/assets/1d7f7bd0-076a-4cd7-8096-d40dfc447521)


## RESULT:
The program is executed successfully
