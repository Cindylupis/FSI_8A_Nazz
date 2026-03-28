## Descripción

We found this [file](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery). Recover the flag.

Este reto, **c0rrupt**, es un ejercicio clásico de **Análisis de Cabeceras (File Headers)**. Aquí no se trata de buscar caracteres invisibles, sino de reparar un archivo que está "roto" porque alguien cambió sus bytes iniciales.
## Solución

**Solución 1 - Usando zsteg online
```
picoCTF{h1d1ng_1n_th3_b1t5}
```

#### NOTAS
En la estructura de un PNG, después del CRC de un bloque (en este caso el `pHYs`), los siguientes 4 bytes **deben ser la longitud (Length)** del siguiente bloque. Ese valor `AA AA FF A5` es un número gigantesco (más de 2.8 gigabytes), por eso `pngcheck` te dice **"too large"**.