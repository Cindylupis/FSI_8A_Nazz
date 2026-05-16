## Descripción

We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?

Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar).

The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
## Solución

**Solución 1
```
### El Cifrado (ROT13)

Al ser un reto de criptografía básica, esta contraseña no es un texto aleatorio, sino la bandera cifrada con **ROT13** (un cifrado César clásico donde cada letra se desplaza 13 posiciones en el alfabeto).

- `c` + 13 = `p` 
- `v` + 13 = `i`  
- `p` + 13 = `c`  
- `b` + 13 = `o`  
- `P` + 13 = `C`  
- `G` + 13 = `T`  
- `S` + 13 = `F`
  
Flag :picoCTF{C7r1F_54V35_71M3}

```

#### NOTAS
Búsqueda de correspondencia de índices entre listas (diccionarios de contraseñas filtradas) y decodificación de texto utilizando el cifrado de sustitución simple ROT13