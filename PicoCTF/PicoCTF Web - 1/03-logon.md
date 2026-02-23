### **Descripción**

The factory is hiding things from all of its users.Can you login as Joe and find what they've been looking at? http://fickle-tempest.picoctf.net:51088
## Solución

**Solución 1- 
``` 
picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}


```

#### NOTAS
- ### 1. Localiza la Cookie

En el menú de la izquierda de esa misma pantalla rosa que tienes abierta:

- Haz clic en la pequeña flecha junto a **"Cookies"**.
- Selecciona la dirección del sitio: `http://fickle-tempest.picoctf.net:51088`.

### 2. Cambia tu identidad

Una vez que hagas clic ahí, aparecerá una tabla a la derecha. Busca la fila que dice **`admin`**:

- Verás que en la columna "Value" (Valor) dice **`False`**.
- Dale doble clic a ese `False` y escribe **`True`**.
- Presiona Enter para asegurar el cambio.

### 3. ¡Captura la bandera!

- Sin cerrar las herramientas de desarrollador, regresa a la página y presiona **F5** (o el botón de refrescar) en tu ThinkPad.
- El servidor ahora leerá tu cookie modificada, pensará que eres el administrador y te mostrará la bandera.