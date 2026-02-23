### **Descripción**

How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 53316`
## Solución

**Solución 1- usando terminal
``` 
NazaretEsquivel-picoctf@webshell:~$ nc titan.picoctf.net 53316

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 00001110
Binary Number 2: 10111101


Question 1/6:
Operation 1: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00001100
Correct!

Question 2/6:
Operation 2: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11001011
Correct!

Question 3/6:
Operation 3: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01011110
Correct!

Question 4/6:
Operation 4: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 101001010110
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 00011100
Correct!

Question 6/6:
Operation 6: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10111111
Correct!

Enter the results of the last operation in hexadecimal: BF

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}


```

#### NOTAS
- #### Cómo convertirlo:

1. Divide el binario en dos grupos de 4 bits (nibbles): `1011` y `1111`.
    
2. `1011` en hexadecimal es **B**.
    
3. `1111` en hexadecimal es **F**.