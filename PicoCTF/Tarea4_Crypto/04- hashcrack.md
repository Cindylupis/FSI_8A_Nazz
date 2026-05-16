## Descripción

A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server?

Access the server using `nc verbal-sleep.picoctf.net 52788
## Solución

**Solución 1
```
pasword123
letmein
qwerty098

Flag :picoCTF{UseStr0nG_h@shEs_&PaSswDs!_4de57566}

```

#### NOTAS
Identificación de hash MD5 por su longitud (32 caracteres) y recuperación de la contraseña en texto plano mediante ataques de diccionario usando bases de datos online (CrackStation) o herramientas locales (John the Ripper)