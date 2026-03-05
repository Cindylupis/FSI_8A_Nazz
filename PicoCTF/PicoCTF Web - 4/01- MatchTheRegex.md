## Descripción

How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:65026/).
## Solución

**Solución 1
```
En el campo de **input text**, se escribe: `picoCTF`
SUBMIT

saturn.picoctf.net:65026 dice
picoCTF{succ3ssfully_matchtheregex_8ad436ed}

```

#### NOTAS
- - `// ^p.....F!?`
Esta es la **expresión regular** (Regex) que el servidor espera que cumplas. Vamos a desglosarla:
- `^` indica el inicio de la cadena.
- `p` es la primera letra obligatoria.
- Los cinco puntos `.....` representan cualquier combinación de 5 caracteres.
- `F` es la letra con la que debe terminar esa secuencia.