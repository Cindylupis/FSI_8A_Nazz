## Descripción

We found this [file](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery). Recover the flag.

Este reto, **c0rrupt**, es un ejercicio clásico de **Análisis de Cabeceras (File Headers)**. Aquí no se trata de buscar caracteres invisibles, sino de reparar un archivo que está "roto" porque alguien cambió sus bytes iniciales.
## Solución

**Solución 1 - Usando zsteg online
```
picoCTF{h1d1ng_1n_th3_b1t5}
```

#### NOTAS
### El Concepto: "Magic Bytes"

Todos los archivos (PNG, JPG, PDF) comienzan con unos bytes específicos llamados **Magic Bytes**. Si esos bytes se alteran, tu computadora no sabe qué programa usar para abrir el archivo y dice que está dañado.

Todo archivo **PNG** debe comenzar con 8 bytes específicos. Si estos están mal, ningún programa podrá abrirlo.