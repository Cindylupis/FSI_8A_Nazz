### **Descripción**

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución

**Solución 1- usando python**

pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
``` 
NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.py
--2026-02-17 20:20:56--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.72, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py            100%[=====================>]   1.31K  --.-KB/s    in 0s      

2026-02-17 20:20:56 (1021 MB/s) - 'level3.py' saved [1337/1337]

NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
--2026-02-17 20:21:11--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.18, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc  100%[=====================>]      31  --.-KB/s    in 0s      

2026-02-17 20:21:11 (7.70 MB/s) - 'level3.flag.txt.enc' saved [31/31]

NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
--2026-02-17 20:21:32--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.72, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin      100%[=====================>]      16  --.-KB/s    in 0s      

2026-02-17 20:21:33 (7.62 MB/s) - 'level3.hash.bin' saved [16/16]

NazaretEsquivel-picoctf@webshell:~$ nano level3.hash.bin
NazaretEsquivel-picoctf@webshell:~$ nano level3.py
NazaretEsquivel-picoctf@webshell:~$ bvi level3.hash.bin

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
NazaretEsquivel-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: f09e
That password is incorrect
NazaretEsquivel-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 4dcf
That password is incorrect
NazaretEsquivel-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

```

#### NOTAS
- **No se guardan las contraseñas**, se guardan sus **hashes**.
    
- Un hash es una función de una sola vía; no puedes "descifrar" el archivo `.bin` para obtener la clave, pero puedes comparar hashes para verificar que la clave es correcta.