## Descripción

Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:58661/) to find the flag

Localizar una cadena de texto oculta en el código fuente de una aplicación web y decodificarla para obtener la flag.
## Solución

**Solución 1
```
<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9">

NazaretEsquivel-picoctf@webshell:~$ echo cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9 | base64 -d
picoCTF{web_succ3ssfully_d3c0ded_07b91c79}NazaretEsquivel-
```

#### NOTAS
- **Base64 Encoding:** Un método para representar datos binarios en formato de texto ASCII. Se identifica comúnmente por el uso de caracteres `A-Z`, `a-z`, `0-9`, `+`, `/` y el relleno `=`.
- **CLI Decoding:** Uso de la terminal para procesar datos de forma rápida.

## Procedimiento (Paso a paso)

1. **Fase de Reconocimiento:** Se exploró el sitio web, encontrando una pista en la página "About" que sugería inspeccionar el código.
2. **Localización:** Usando el Inspector, se halló un atributo personalizado en una etiqueta `<section>`:
3. **Explotación (Terminal):** Se utilizó la terminal de picoCTF para decodificar la cadena directamente con el siguiente comando:
```
echo cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9 | base64 -d
```
4. **Resultado:** El comando devolvió la flag en texto plano.