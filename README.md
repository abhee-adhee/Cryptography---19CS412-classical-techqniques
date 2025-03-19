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
CaearCipher.
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
OUTPUT:
Simulating Caesar Cipher


Input : Anna University
Encrypted Message : Dqqd Xqlyhuvlwb Decrypted Message : Anna University

## RESULT:
The program is executed successfully

---------------------------------
