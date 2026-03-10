## Descripción

Can you get the flag?Go to this [website](http://saturn.picoctf.net:65518/) and see what you can discover.
## Solución

**Solución 1
```
Cookie:
picoCTF{gr4d3_A_c00k13_65fd1e1a}
```

#### NOTAS
Las cookies se utilizan para mantener el "estado" de una sesión. Si un desarrollador confía ciegamente en los datos de una cookie para definir privilegios (como quién es admin), un atacante puede editarlas localmente para escalar privilegios.

## Procedimiento

- **Localización:** Pestaña `Application` -> `Cookies` en las DevTools.
- **Variable:** `isAdmin`.
- **Modificación:** Cambiar el valor de `0` a `1`.
- **Resultado:** El servidor concede acceso de administrador basándose únicamente en el valor modificado de la cookie.

## ⚠️ Lección de Seguridad

Nunca se debe confiar en los datos del lado del cliente para la autorización. La verificación de si alguien es administrador debe hacerse siempre en el servidor mediante sesiones seguras o tokens firmados (como JWT).