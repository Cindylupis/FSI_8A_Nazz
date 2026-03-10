## Descripción

The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:58919/) out.
## Solución

**Solución 1
```
http://saturn.picoctf.net:58919/robots.txt
 |
 |
 v
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/

http://saturn.picoctf.net:58919/js/myfile.txt
  |
  |
  v
picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}


```

#### NOTAS
A veces los desarrolladores intentan ocultar rutas sensibles en el archivo `robots.txt` usando codificación básica para que no sea legible a simple vista por humanos, pero los atacantes pueden decodificarlo fácilmente.

## Procedimiento

1. **Acceso:** Se encontró el archivo `robots.txt`.
2. **Análisis:** Se identificó una cadena en Base64: `anMvbXlmaWxlLnR4dA==`.
3. **Decodificación:** - Entrada: `anMvbXlmaWxlLnR4dA==`
       Salida: `js/myfile.txt`        
4. **Explotación:** Al navegar a la ruta descubierta, se obtiene la bandera.

La codificación (Base64) **no es lo mismo** que la encriptación. La codificación solo cambia el formato del texto para que sea compatible con ciertos sistemas; cualquier persona puede revertirlo sin necesidad de una llave.