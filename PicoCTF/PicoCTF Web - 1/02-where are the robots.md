### **Descripción**

Can you find the robots? http://fickle-tempest.picoctf.net:63784
## Solución

**Solución 1- usando python**
``` 
# Welcome
Where are the robots?

http://fickle-tempest.picoctf.net:63784/robots.txt
User-agent: *
Disallow: /cc6b1.html

http://fickle-tempest.picoctf.net:63784/cc6b1.html
Guess you found the robots  
picoCTF{ca1cu1at1ng_Mach1n3s_cc6b1}

```

#### NOTAS
- ### ¿Qué es `robots.txt`?

Es un archivo de texto simple que los administradores de sitios web colocan en el directorio raíz de su servidor (ejemplo: `tu-sitio.com/robots.txt`). Su función principal es dar instrucciones a los **rastreadores web** (como el bot de Google o Bing) sobre a qué carpetas o archivos **no deben acceder** para indexar en los buscadores.