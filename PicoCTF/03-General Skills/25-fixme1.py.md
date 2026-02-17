### **Descripción**
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/27/fixme1.py
NazaretEsquivel-picoctf@webshell:~$ python fixme1.py
  File "/home/NazaretEsquivel-picoctf/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
NazaretEsquivel-picoctf@webshell:~$ nano fixme1.py
NazaretEsquivel-picoctf@webshell:~$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

```

#### NOTAS
**fixme1.py** | `IndentationError` | Eliminar espacios innecesarios al inicio de la línea.
Esto significa que la línea donde se imprime la flag tiene espacios de más que no deberían estar ahí.