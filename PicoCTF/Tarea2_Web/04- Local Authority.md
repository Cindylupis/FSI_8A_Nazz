## Descripción

Can you get the flag?Go to this [website](http://saturn.picoctf.net:55593/) and see what you can discover.

## 🎯 Objetivo

Acceder a una zona restringida encontrando las credenciales de inicio de sesión ocultas en los archivos del cliente.
## Solución 

**Solución 1
```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}


picoCTF{j5_15_7r4n5p4r3n7_a8788e61}

```

## Conceptos Clave

- **Client-Side Validation:** Cuando la lógica de seguridad ocurre en el navegador del usuario y no en el servidor. Es una práctica muy insegura.

- **Sources/Debugger:** Pestaña de las herramientas de desarrollador que permite ver todos los archivos cargados (HTML, CSS, JS).

## NOTAS ##
- **Análisis de JS:** Buscar lógica condicional (`if/else`) que compare inputs del usuario con strings fijos.
- **REGLA DE ORO:** Nunca, bajo ninguna circunstancia, se deben guardar contraseñas o llaves API directamente en archivos JavaScript, ya que cualquier usuario puede verlas con `Ctrl+U` o `F12`.
- El nombre "Local Authority" es una pista de que la "autoridad" (quien decide si entras o no) es **local** (tu propio navegador).