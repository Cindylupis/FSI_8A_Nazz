### **Descripción**

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ nano level1.py
NazaretEsquivel-picoctf@webshell:~$ python3 level1.py
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
NazaretEsquivel-picoctf@webshell:~$ 
Webshell session has ended.

```

#### NOTAS
En seguridad de la información, esto se llama **"Information Disclosure"** por malas prácticas de desarrollo. El programador confió en que el usuario no vería el código fuente, pero en seguridad siempre asumimos que el atacante puede ver cómo funciona nuestro software por dentro.