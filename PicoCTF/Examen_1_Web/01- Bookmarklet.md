## Descripción

Why search for the flag when I can make a bookmarklet to print it for me?Browse [here](http://titan.picoctf.net:50806/), and find the flag!
## Solución

**Solución 1
```
javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÓÇ¡¥Ìí";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();

picoCTF{p@g3_turn3r_0c0d211f}    

```

#### NOTAS
- **Concepto:** Ejecución de JavaScript en el lado del cliente (Client-Side Execution).
- **Técnica:** Uso de **Bookmarklets**, que son scripts embebidos en una URL con el esquema `javascript:`.

**Seguridad del Navegador:**
- **Self-XSS Protection:** Medida de seguridad que impide pegar código en la consola (se desbloquea con el comando `allow pasting` en Chrome).
- **Contexto de Ejecución:** El código debe ejecutarse en la misma pestaña de la aplicación objetivo para acceder a sus variables y funciones.