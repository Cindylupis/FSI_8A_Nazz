### **Descripción**
Can you look at the data in this binary? The bash script might help![static](https://challenge-files.picoctf.net/c_wily_courier/a7a487d82414dabf57a3ec5db604ae18c17b11406225839247539d5edb709957/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/a7a487d82414dabf57a3ec5db604ae18c17b11406225839247539d5edb709957/ltdis.sh)

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget [enlace_de_static]
http://[enlace_de_static]: Invalid IPv6 numeric address.
NazaretEsquivel-picoctf@webshell:~$ wget [enlace_de_ltdis.sh]
http://[enlace_de_ltdis.sh]: Invalid IPv6 numeric address.
NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/a7a487d82414dabf57a3ec5db604ae18c17b11406225839247539d5edb709957/static
--2026-02-11 17:44:48--  https://challenge-files.picoctf.net/c_wily_courier/a7a487d82414dabf57a3ec5db604ae18c17b11406225839247539d5edb709957/static
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.40, 3.160.5.64, 3.160.5.18, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16776 (16K) [application/octet-stream]
Saving to: 'static'

static               100%[=====================>]  16.38K  --.-KB/s    in 0.004s  

2026-02-11 17:44:49 (3.96 MB/s) - 'static' saved [16776/16776]

NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/a7a487d82414dabf57a3ec5db604ae18c17b11406225839247539d5edb709957/ltdis.sh
--2026-02-11 17:45:02--  https://challenge-files.picoctf.net/c_wily_courier/a7a487d82414dabf57a3ec5db604ae18c17b11406225839247539d5edb709957/ltdis.sh
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh             100%[=====================>]     785  --.-KB/s    in 0s      

2026-02-11 17:45:02 (124 MB/s) - 'ltdis.sh' saved [785/785]

NazaretEsquivel-picoctf@webshell:~$ bash ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
NazaretEsquivel-picoctf@webshell:~$ grep picoCTF static.ltdis.strings.txt
   3020 picoCTF{d15a5m_t34s3r_20335e41}

```

#### NOTAS
- El archivo `.x86_64.txt` contiene instrucciones de lenguaje ensamblador (el "pensamiento" del procesador).

- El archivo `.strings.txt` contiene todos los textos legibles que el script encontró, lo cual es el lugar perfecto para esconder una **flag**.