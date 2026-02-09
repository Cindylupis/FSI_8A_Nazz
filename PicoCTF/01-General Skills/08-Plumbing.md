### **Descripción**
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?

Additional details will be available after launching your challenge instance.
Connect to fickle-tempest.picoctf.net 56383.
## Solución

**Solución 1- usando python**
``` :~$ python3
NazaretEsquivel-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 56383 | grep pico
picoCTF{digital_plumb3r_8c8f3412}

NazaretEsquivel-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 56383 > salida
NazaretEsquivel-picoctf@webshell:~$ cat salida | grep pico
```

#### NOTAS
"|" ES el pipe redirige la salida de un comando a la entrada del otro