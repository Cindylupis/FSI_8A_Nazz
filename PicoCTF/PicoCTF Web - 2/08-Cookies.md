## Descripción

Who doesn't love cookies? Try to figure out the best one.http://wily-courier.picoctf.net:56895/
## Solución

**Solución 1
```
 Flag:picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}


```

#### NOTAS
-  Inspeccionar y modificar
   la pestaña **Application** -> **Cookies**.
   Verás una cookie llamada **`name`**. Nota que su valor es un número (probablemente `0` o `1`).


- El ataque de "Fuerza Bruta" manual
  Cambiar el valor de la cookie `name` a **`1`**, presionar Enter y refrescar la página 
  Aparece una galleta diferente.
  Seguir probando: `2`, `3`, `4`... hasta encontrar el número que corresponde a la galleta del administrador que en este ejercicio fue en 18.