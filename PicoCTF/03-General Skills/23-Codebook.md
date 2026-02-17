### **Descripción**
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2026-02-17 05:42:27--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.77, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py              100%[=====================>]   1.25K  --.-KB/s    in 0s      

2026-02-17 05:42:27 (21.0 MB/s) - 'code.py' saved [1278/1278]

NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2026-02-17 05:42:39--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.72, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt         100%[=====================>]      27  --.-KB/s    in 0s      

2026-02-17 05:42:39 (1.70 MB/s) - 'codebook.txt' saved [27/27]

NazaretEsquivel-picoctf@webshell:~$ python3 code.py
picoCTF{c0d3b00k_455157_197a982c}

```

#### NOTAS
El script procesará los datos (usando la función `str_xor` internamente) y te mostrará la bandera en formato `picoCTF{...}`