### **Descripción**
Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way.The flag is in this [file](https://challenge-files.picoctf.net/c_fickle_tempest/b8915fc817a2cd58e83d7e779515ed3f898738d12cf1974086f8ba3f515ae3cf/file).

## Solución

**Solución 1- usando python**
``` :~$ python3
NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/b8915fc817a2cd58e83d7e779515ed3f898738d12cf1974086f8ba3f515ae3cf/file
--2026-02-09 18:36:57--  https://challenge-files.picoctf.net/c_fickle_tempest/b8915fc817a2cd58e83d7e779515ed3f898738d12cf1974086f8ba3f515ae3cf/file
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.40, 3.160.5.18, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14546 (14K) [application/octet-stream]
Saving to: 'file'

file                100%[==================>]  14.21K  --.-KB/s    in 0.001s  

2026-02-09 18:36:57 (10.4 MB/s) - 'file' saved [14546/14546]

NazaretEsquivel-picoctf@webshell:~$ grep pico file
picoCTF{grep_is_good_to_find_things_beD770f5}
```

#### NOTAS
grep --> encuentra una cadena en una archivo de texto.