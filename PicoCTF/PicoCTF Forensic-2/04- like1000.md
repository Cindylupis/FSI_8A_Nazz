## Descripción

There's something in the [building](https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png). Can you retrieve the flag?

La **Esteganografía** es el arte de ocultar mensajes dentro de otros objetos, como imágenes.

A diferencia del anterior, aquí la imagen sí se ve bien, pero tiene información "entre los píxeles".
## Solución

**Solución 1 - Usando zsteg online
```
picoCTF{h1d1ng_1n_th3_b1t5}
```

#### NOTAS
### Herramientas utilizadas

- **StegOnline / zsteg**: Herramientas especializadas en detectar datos ocultos en los bits de una imagen.

### Resolución

1. **Teoría:** Se sospechó de **LSB (Least Significant Bit)**, una técnica donde se usan los bits menos significativos de los píxeles para guardar información.
2. **Ejecución:** Al cargar la imagen en **StegOnline** y realizar una extracción de datos (o usar `zsteg` en terminal), se analizó el **Bit 0** de los canales **Red, Green y Blue**.
3. **Resultado:** El mensaje oculto apareció directamente como texto plano entre los datos extraídos.

### Concepto: Esteganografía LSB

En computación, los colores se representan a menudo con 8 bits (valores de 0 a 255).

- Si un píxel tiene un valor de Rojo de **255** (`11111111`) y cambiamos el último bit a `0` (**254** o `11111110`), el cambio de color es **0.39%**, imposible de ver para el ojo humano.
- Ese bit "sobrante" se usa para esconder la bandera.