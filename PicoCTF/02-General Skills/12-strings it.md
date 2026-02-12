### **Descripción**
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/a35dc624cfda858ed12a4bce57f832dad3b433bad6cde2b98e25fae4bc8ff760/strings) without running it?

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/a35dc624cfda858ed12a4bce57f832dad3b433bad6cde2b98e25fae4bc8ff760/strings
--2026-02-11 17:25:00--  https://challenge-files.picoctf.net/c_fickle_tempest/a35dc624cfda858ed12a4bce57f832dad3b433bad6cde2b98e25fae4bc8ff760/strings
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.40, 3.160.5.18, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 784424 (766K) [application/octet-stream]
Saving to: 'strings.3'

strings.3            100%[=====================>] 766.04K  1.78MB/s    in 0.4s    

2026-02-11 17:25:01 (1.78 MB/s) - 'strings.3' saved [784424/784424]

NazaretEsquivel-picoctf@webshell:~$ strings strings.3 | grep picoCTF
picoCTF{5tRIng5_1T_60eA8fdA}

```

#### NOTAS
En python se abre el archivo txt y con el comando strings strings.3 | grep picoCTF se obtiene la bandera