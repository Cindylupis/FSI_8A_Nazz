### **Descripción**

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/15/level2.py
--2026-02-17 20:13:58--  https://artifacts.picoctf.net/c/15/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py            100%[=====================>]     914  --.-KB/s    in 0s      

2026-02-17 20:13:58 (928 MB/s) - 'level2.py' saved [914/914]

NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
--2026-02-17 20:14:12--  https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.33, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc  100%[=====================>]      31  --.-KB/s    in 0s      

2026-02-17 20:14:12 (34.3 MB/s) - 'level2.flag.txt.enc' saved [31/31]

NazaretEsquivel-picoctf@webshell:~$ nano level2.py
NazaretEsquivel-picoctf@webshell:~$ python3
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))
39ce
>>> exit()
NazaretEsquivel-picoctf@webshell:~$ python3 level2.py
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}

```

#### NOTAS
Este nivel te enseña sobre la **Ofuscación**. A veces, los desarrolladores intentan ocultar secretos usando codificaciones simples (como hexadecimal o Base64) pensando que eso es "seguridad". Sin embargo, la ofuscación **no es criptografía**, es solo un pequeño obstáculo que no detiene a nadie con herramientas básicas.
