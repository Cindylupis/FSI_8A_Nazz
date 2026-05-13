## Descripción

Can you figure out how this program works to get the flag?

Connect to the program with netcat:

`$ nc saturn.picoctf.net 55533`

The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/524/picker-III.py).
## Solución

**Solución 1
```

Flag :picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_01672a61}
```

#### NOTAS
Al buscar en Google, descubrí que sí podíamos "modificar" la tabla: simplemente reemplazando el contenido de win() en una de las variables llamadas.