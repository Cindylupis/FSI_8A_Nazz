## Descripción

Can you decrypt this message?

Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".
## Solución

**Solución 1
```

Flag :picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}

```

#### NOTAS
Vigenère es un cifrado de sustitución **polialfabética**. Esto significa que la cantidad de posiciones que se desplaza cada letra cambia constantemente basándose en la palabra clave que te dieron: **`CYLAB`**.

Resolución de un cifrado de Vigenère (sustitución polialfabética). Se utilizó la clave conocida (`CYLAB`) para revertir el desplazamiento variable de los caracteres alfabéticos, respetando el formato, los números y los símbolos especiales intactos.