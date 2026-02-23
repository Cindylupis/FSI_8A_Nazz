### **Descripción**

This website can be rendered only by picobrowser, go and catch the flag!http://fickle-tempest.picoctf.net:59074

**Solución 1- 
``` 
- Abrir el enlace del reto en Chrome o Firefox.
    
- Presiona `F12` y ve a la pestaña **Network** (Red).
    
- Busca los tres puntos verticales (o el icono de engranaje) y busca **Network conditions**.
    
- Desmarca "Use browser default" en la sección de **User agent**.
    
- En el cuadro de texto de esa misma seccion, escribe simplemente: picobrowser
    
- Refresca la página y haz clic en el botón "Flag".

picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}
```

#### NOTAS
- Este reto te enseña que las validaciones de seguridad basadas en datos que el cliente (el usuario) puede modificar son **vulnerabilidades críticas**. En seguridad, esto se llama **"Insecure Client-Side Validation"**. Nunca debemos confiar en lo que el navegador dice ser, porque un atacante puede cambiar su `User-Agent` en segundos.