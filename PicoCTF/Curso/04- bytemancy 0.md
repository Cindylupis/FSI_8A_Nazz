## Descripción

Can you conjure the right bytes? The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_candy_mountain/87600c43f9f35274d6269e8237fcd84602c631a5ebcf5251266fb11dc0e94f3b/app.py).Connect to the program with netcat:`$ nc candy-mountain.picoctf.net 64694`

### Análisis del Reto

El objetivo es enviar los bytes correctos al programa que está corriendo en el servidor para que nos entregue la bandera. El comando clave aquí es `nc` (netcat), la "navaja suiza" de las redes.

## Solución

**Solución 1 - Usando terminal WebShell
```
NazaretEsquivel-picoctf@webshell:~$ nc candy-mountain.picoctf.net 64694
⊹──────[ BYTEMANCY-0 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101, 101, 101, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
==> eee
picoCTF{pr1n74813_ch4r5_4daf27d8}
```

#### NOTAS
Resolución 
1. **Conexión Remota:** Se utilizó `netcat` desde la Web Shell de picoCTF para establecer un socket TCP. `nc candy-mountain.picoctf.net 64694` 
2. **Desafío del Servidor:** El programa solicitó una secuencia de bytes basada en valores decimales ASCII (101, 101, 101). 
3. **Conversión:** - Valor Decimal 101 = Carácter 'e' (ASCII). - Cadena requerida: "eee". 
4. **Resultado:** Al enviar la cadena, el servidor validó la entrada y liberó el buffer que contenía la bandera.