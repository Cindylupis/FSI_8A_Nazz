### **Descripción**
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?
Connect with nc fickle-tempest.picoctf.net 61151.

## Solución
**Solución 1- usando cyberchef**
https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDExMDAgMDExMDAwMDEgMDExMDExMDEgMDExMTAwMDAK
picoCTF{learning_about_converting_values_aa2bA794}

**Solución 2- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 61151
Let us see how data is stored
lamp
Please give the 01101100 01100001 01101101 01110000 as a word.
...
you have 45 seconds.....

Input:
lamp
Please give me the  o154 o151 o172 o141 o162 o144 as a word.
Input:
lizard
Please give me the 636f6d7075746572 as a word.
Input:
computer
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_aa2bA794}
>>> 
```

#### NOTAS
Cyberchef nos permitió descifrar las palabras ocultas que obtuvimos en la terminal en menis de 45 segundos cada una  
En python se ingresan la palabras que nos dio el cyberchef y así obtuvimos la bandera