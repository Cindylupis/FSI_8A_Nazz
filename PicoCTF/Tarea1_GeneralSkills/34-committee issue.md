### **Descripción**

I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/138/challenge.zip)
## Solución

**Solución 1- terminal**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/138/challenge.zip
--2026-02-23 16:50:28--  https://artifacts.picoctf.net/c_titan/138/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.18, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19199 (19K) [application/octet-stream]
Saving to: 'challenge.zip.3'

challenge.zip      100%[=====================>]  18.75K  --.-KB/s    in 0.002s  

2026-02-23 16:50:28 (11.3 MB/s) - 'challenge.zip.3' saved [19199/19199]

NazaretEsquivel-picoctf@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
  inflating: drop-in/.git/description  
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
  inflating: drop-in/.git/info/exclude  
 extracting: drop-in/.git/refs/heads/master  
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
 extracting: drop-in/.git/objects/0e/0fefcdc9c9722914a7a9ecab1e88784f005eeb  
 extracting: drop-in/.git/objects/5b/222fb49097fe9874695e8cc7cd9a6c80886017  
 extracting: drop-in/.git/objects/b5/62f0b425907789d11d2fe2793e67592dc6be93  
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
 extracting: drop-in/.git/objects/42/942c9c605b30100f5d859ef6e172027447c0db  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
  inflating: drop-in/.git/logs/HEAD  
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
NazaretEsquivel-picoctf@webshell:~$ cd drop-in
NazaretEsquivel-picoctf@webshell:~/drop-in$ git log
NazaretEsquivel-picoctf@webshell:~/drop-in$ git show b562f0b
   |
   |
   v
commit b562f0b425907789d11d2fe2793e67592dc6be93
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    create flag

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..0e0fefc
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+picoCTF{s@n1t1z3_c785c319}
```

#### NOTAS
- **borrar el contenido no borra el historial**. Un atacante solo necesita acceso a la carpeta `.git` para reconstruir cada secreto que alguna vez estuvo ahí.
- **Ver el historial**: Ejecuta `git log`.
	Busca un commit que mencione algo sobre la bandera (por ejemplo: "add flag", "oops", o "remove flag").