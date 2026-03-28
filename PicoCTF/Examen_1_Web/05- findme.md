## Descripción

Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:60537/).

**Solución 1
```
http://saturn.picoctf.net:60537/next-page/id=cGljb0NURntwcm94aWVzX2Fs
http://saturn.picoctf.net:60537/next-page/id=bF90aGVfd2F5X2JlNzE2ZDhlfQ==

cGljb0NURntwcm94aWVzX2FsbF90aGVfd2F5X2JlNzE2ZDhlfQ==

picoCTF{proxies_all_the_way_be716d8e}
```

#### NOTAS
- **Concepto:** Fuga de información en redirecciones **HTTP 302**.
- **Técnica:** El servidor envía fragmentos de la bandera como parámetros de URL (`?id=...`) durante los saltos de redirección.
- **Análisis:** Al ser saltos automáticos y rápidos, solo son visibles activando **Preserve Log** en la pestaña **Network**.
- **Identificación:** Las cadenas terminadas en `==` o que empiezan con `cGlj` suelen ser **Base64**.