## Descripción

We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:51204/).

## Concepto
La vulnerabilidad aquí es la **exposición de directorios sensibles**. Los desarrolladores a menudo asumen que si no hay un enlace directo a una carpeta en el menú principal, nadie la encontrará. Sin embargo, mediante la inspección manual del código fuente o herramientas automáticas, estas rutas "ocultas" salen a la luz.
## Solución

**Solución 1
```
|   |
|---|
|<!DOCTYPE html>|
|<html>|
|<head>|
|<title></title>|
|<link rel="stylesheet" href="[mycss.css](http://saturn.picoctf.net:51204/secret/hidden/superhidden/mycss.css)" />|
|</head>|
||
|<body>|
|<h1>Finally. You found me. But can you see me</h1>|
|<h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_51b260fe}</h3>|
|</body>|
|</html>|
||

```

#### NOTAS
## Procedimiento

- **Ruta de descubrimiento:** Se sigue el rastro de carpetas anidadas leyendo el HTML de cada nivel.
- **Cadena de directorios:** `index` -> `/secret/` -> `/hidden/` -> `/superhidden/`.
- **Hallazgo final:** La bandera suele estar escondida en el código fuente de la página más profunda o en un archivo relacionado (como un `.js` o `.css`).

Para prevenir esto en producción, se deben configurar los servidores web (como Nginx o Apache) para denegar el listado de directorios y asegurar que no haya rutas predecibles o comentadas en el código que llega al cliente.