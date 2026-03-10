## Descripción

This is a really weird text file. Can you find the flag?Get the flag from [TXT](https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt).

En Windows, nos han acostumbrado a creer que la extensión (`.txt`, `.jpg`, `.exe`) define al archivo. **¡Pero eso es mentira!** Un hacker puede renombrar un virus como `foto.jpg` y seguirá siendo un ejecutable.

Los sistemas operativos de verdad (como el Linux ) miran los **primeros bytes** del archivo para saber qué es. Esos bytes se llaman "Magic Bytes".
## Solución

**Solución 1
```
usuarionazz890@DESKTOP-EHL2SJN:~$ cd /mnt/c/Users/Usuario/Downloads
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads$ file flag.txt
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads$ mv flag.txt flag.png

picoCTF{now_you_know_about_extensions}

```

#### NOTAS
### Herramientas utilizadas

- **Terminal (WSL/Linux)**
- **Comando `file`**: Para identificar la naturaleza real del archivo.
- **Comando `mv`**: Para corregir la extensión.

### Resolución

1. **Identificación:** Al ejecutar `file flag.txt`, la terminal reveló que los metadatos y la firma del archivo correspondían a una imagen: `PNG image data`.
2. **Corrección:** Se renombró el archivo para que el sistema operativo pudiera interpretarlo correctamente:
  
   mv flag.txt flag.png
  
1. **Extracción:** Al abrir la imagen `flag.png`, la bandera era visible en el contenido visual.

###  Key Learning: Magic Bytes

Los **Magic Bytes** son los primeros bytes de un archivo que actúan como una firma única.

- **PNG:** Siempre empieza con `89 50 4E 47` (en hex).
- **PDF:** Siempre empieza con `%PDF` (`25 50 44 46`).
- **JPEG:** Empieza con `FF D8 FF`.

