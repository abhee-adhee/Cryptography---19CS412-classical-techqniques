# Cryptography---19CS412-classical-techqniques
# Caeser Cipher
Caeser Cipher using with different key values

### NAME: ABINAV AADITYA S
### REGISTER NO.: 212224040008

# AIM:

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.


## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

1.	In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2.	For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
3.	The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
    scheme, A = 0, B = 1, Z = 25.
4.	Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
5.	Decryption is performed similarly,
                       Dn (x)=(x - n) mod26


## PROGRAM:
PROGRAM:
CaesarCipher.
```
def caesar_cipher(text, shift):
    result = ""
    for char in text:
        if char.isalpha():  
            start = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - start + shift) % 26 + start)
        else:
            result += char 
    return result
message = input("Enter the message: ")
key = int(input("Enter the shift value: "))
encrypted_message = caesar_cipher(message, key)
print("Encrypted Message:", encrypted_message)
decrypted_message = caesar_cipher(encrypted_message, -key)
print("Decrypted Message:", decrypted_message)
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/08c27ac0-f6a6-404c-820b-ad5992b96d21)


## RESULT:
The program is executed successfully

---------------------------------
---------------------------------

# PlayFair Cipher
Playfair Cipher using with different key values

# AIM:

To implement a program to encrypt a plain text and decrypt a cipher text using play fair Cipher substitution technique.

 
## DESIGN STEPS:

### Step 1:

Design of PlayFair Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code


## PROGRAM:
```
import numpy as np

def hill_encrypt(plaintext, key_matrix):
    plaintext = plaintext.upper().replace(" ", "")
    n = len(key_matrix)
    
    while len(plaintext) % n != 0:
        plaintext += "X"  # Padding with 'X' if needed

    text_vector = [ord(c) - ord('A') for c in plaintext]
    encrypted_text = ""

    for i in range(0, len(text_vector), n):
        chunk = np.array(text_vector[i:i+n]).reshape(n, 1)
        encrypted_chunk = np.dot(key_matrix, chunk) % 26
        encrypted_text += ''.join(chr(int(c) + ord('A')) for c in encrypted_chunk.flatten())

    return encrypted_text

key_matrix = np.array([[6, 24, 1], [13, 16, 10], [20, 17, 15]])  # Example 3x3 key matrix
message = "ACT"
encrypted = hill_encrypt(message, key_matrix)
print("Encrypted Message:", encrypted)
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/3f052df2-af8d-4347-aba1-78d284a6348b)


## RESULT:
The program is executed successfully


---------------------------

# Hill Cipher
Hill Cipher using with different key values

# AIM:

To develop a simple C program to implement Hill Cipher.

## DESIGN STEPS:

### Step 1:

Design of Hill Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 


## PROGRAM:
PROGRAM:
```
def vigenere_encrypt(plaintext, key):
    key = key.upper()
    plaintext = plaintext.upper()
    encrypted_text = ""
    
    for i in range(len(plaintext)):
        if plaintext[i].isalpha():
            shift = ord(key[i % len(key)]) - ord('A')
            encrypted_text += chr((ord(plaintext[i]) - ord('A' )+ shift) % 26 + ord('A'))
        else:
            encrypted_text += plaintext[i]

    return encrypted_text

key = "KEY"
message = "HELLO WORLD"
encrypted = vigenere_encrypt(message, key)
print("Encrypted Message:", encrypted)
```
## OUTPUT:
OUTPUT:
![image](https://github.com/user-attachments/assets/3e41bd84-e8ed-4fdf-9f2e-7106dde1f038)



## RESULT:
The program is executed successfully

-------------------------------------------------

# Vigenere Cipher
Vigenere Cipher using with different key values

# AIM:

To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:

### Step 1:

Design of Vigenere Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 


## PROGRAM:
```
def vigenere_encrypt(plaintext, key):
    key = key.upper()
    plaintext = plaintext.upper()
    encrypted_text = ""
    
    for i in range(len(plaintext)):
        if plaintext[i].isalpha():
            shift = ord(key[i % len(key)]) - ord('A')
            encrypted_text += chr((ord(plaintext[i]) - ord('A' )+ shift) % 26 + ord('A'))
        else:
            encrypted_text += plaintext[i]

    return encrypted_text

key = "KEY"
message = "HELLO WORLD"
encrypted = vigenere_encrypt(message, key)
print("Encrypted Message:", encrypted)
```
## OUTPUT:
OUTPUT :

![image](https://github.com/user-attachments/assets/c408dce4-bbf7-4fa5-b25f-dc05d5127230)

## RESULT:
The program is executed successfully

-----------------------------------------------------------------------

# Rail Fence Cipher
Rail Fence Cipher using with different key values

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## DESIGN STEPS:

### Step 1:

Design of Rail Fence Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:
```
def rail_fence_encrypt(text, rails):
    rail = [['\n' for _ in range(len(text))] for _ in range(rails)]
    direction_down = False
    row, col = 0, 0
    
    for char in text:
        if row == 0 or row == rails - 1:
            direction_down = not direction_down
        rail[row][col] = char
        col += 1
        row += 1 if direction_down else -1

    encrypted_text = "".join(["".join(row) for row in rail]).replace("\n", "")
    return encrypted_text

message = "HELLO WORLD"
rails = 3
encrypted = rail_fence_encrypt(message, rails)
print("Encrypted Message:", encrypted)
```
## OUTPUT:
OUTPUT:
![image](https://github.com/user-attachments/assets/4bfe50d8-6dce-4a3e-b0eb-993eeb4b41ac)

## RESULT:
The program is executed successfully
