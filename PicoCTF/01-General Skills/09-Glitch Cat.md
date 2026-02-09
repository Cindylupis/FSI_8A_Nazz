### **Descripción**
Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 56528`
## Solución

**Solución 1- usando python**
``` :~$ python3
NazaretEsquivel-picoctf@webshell:~$ nc saturn.picoctf.net 56528
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'

NazaretEsquivel-picoctf@webshell:~$ python3
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
'picoCTF{gl17ch_m3_n07_bda68f75}'
```

#### NOTAS
En el interprete de python puedo ejecutar cualquier sentencia de lenguaje 
