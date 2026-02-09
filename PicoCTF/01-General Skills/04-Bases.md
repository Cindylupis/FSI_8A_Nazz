### **Descripción**
What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

## Solución
**Solución 1- usando cyberchef**
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE
picoCTF{l3arn_th3_r0p35}

**Solución 2- usando python**
``` :~$ python3
NazaretEsquivel-picoctf@webshell:~$ python3
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode('bDNhcm5fdGgzX3IwcDM1')
b'l3arn_th3_r0p35'
```

#### NOTAS
Cyberchef es una pagina que me permite decodificar
Base 64