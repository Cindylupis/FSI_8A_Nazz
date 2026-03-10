## Descripción

I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster!Browse [here](http://titan.picoctf.net:56157/), and find the flag!

Se basa en un concepto llamado **minificación**.

Cuando los desarrolladores suben sitios a producción, eliminan todos los espacios, saltos de línea y comentarios para que el archivo pese menos y cargue más rápido. El problema es que, aunque el código sea difícil de leer para un humano, sigue siendo **legible** para el navegador.

## Concepto

La **minificación** es un proceso de optimización, **no de seguridad**. A menudo se confunde con la "ofuscación", pero la minificación solo quita espacios. Si hay secretos (como la flag) en el código fuente, la minificación no los ocultará de un análisis básico.
## Solución

**Solución 1
```
<p class="picoCTF{pr3tty_c0d3_622b2c88}">

```

#### NOTAS
## Procedimiento

- **Acceso:** Inspeccionar el código fuente (`Ctrl + U`).
- **Análisis:** Buscar el patrón de la bandera (`picoCTF{...}`) dentro del bloque de texto comprimido.

En el flujo de trabajo de un ingeniero de software, nunca deben quedar banderas de prueba o credenciales en el código fuente de las vistas (`.html`, `.js`, `.css`), ya que la minificación en el despliegue (deploy) no las protege.