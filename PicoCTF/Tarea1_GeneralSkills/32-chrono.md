### **Descripción**

How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 52577
Username: picoplayer 
Password: bLgSMmbY6X
```
## Solución

**Solución 1- usando python**
``` 
PS C:\Users\Usuario> ssh -p 52577 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:52577 ([13.59.203.175]:52577)' can't be established.
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:52577' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.8.0-1044-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ ls -la /etc/cron.d/
total 8
drwxr-xr-x 1 root root  26 Aug  4  2023 .
drwxr-xr-x 1 root root  66 Feb 23 14:26 ..
-rw-r--r-- 1 root root 102 Feb 13  2020 .placeholder
-rw-r--r-- 1 root root 201 Feb 14  2020 e2scrub_all

picoplayer@challenge:~$ grep -r "pico" /etc/cron*
/etc/crontab:# picoCTF{Sch3DUL7NG_T45K3_L1NUX_1b4d8744}


```

#### NOTAS
- Usar `grep`: buscar la palabra "pico" en todos los archivos de configuración para ir directo al grano: `grep -r "pico" /etc/cron*`