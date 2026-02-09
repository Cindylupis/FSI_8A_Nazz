### **Descripción**
This file has a flag in plain sight (aka "in-the-clear").[flag](https://challenge-files.picoctf.net/c_wily_courier/a2320fa31ee7a0cd35e9ad6685c56de110bb6cc12e048fc9341a42e9066791c8/flag)

## Solución

**Solución 1- usando python**
``` :~$ python3
NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/a2320fa31ee7a0cd35e9ad6685c56de110bb6cc12e048fc9341a42e9066791c8/flag
--2026-02-09 18:45:28--  https://challenge-files.picoctf.net/c_wily_courier/a2320fa31ee7a0cd35e9ad6685c56de110bb6cc12e048fc9341a42e9066791c8/flag
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.18, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                100%[==================>]      34  --.-KB/s    in 0s      

2026-02-09 18:45:28 (2.65 MB/s) - 'flag' saved [34/34]

NazaretEsquivel-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}
```

#### NOTAS
cat -->mostrar un archivo de texto y su bandera directamente