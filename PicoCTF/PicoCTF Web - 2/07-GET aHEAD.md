## Descripción

Find the flag being held on this server to get ahead of the competitionhttp://wily-courier.picoctf.net:54918/
## Solución

**Solución 1- usando terminal
```
 PS C:\Users\Usuario> (curl -Method HEAD -Uri http://wily-courier.picoctf.net:54918/).Headers

Advertencia de seguridad: riesgo de ejecución de script
Invoke-WebRequest analiza el contenido de la página web. El código de script de la página web se puede ejecutar
cuando se analiza la página.
      ACCIÓN RECOMENDADA:
      Usa el modificador -UseBasicParsing para evitar la ejecución de código de script.

      ¿Quieres continuar?

[S] Sí  [O] Sí a todo  [N] No  [T] No a todo  [U] Suspender  [?] Ayuda (el valor predeterminado es "N"): S

Key          Value
---          -----
flag         picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Keep-Alive   timeout=5, max=100
Connection   Keep-Alive
Content-Type text/html; charset=UTF-8
Date         Wed, 25 Feb 2026 18:24:40 GMT
Server       Apache/2.4.38 (Debian)
X-Powered-By PHP/7.2.34
```

#### NOTAS
- **Headers de Respuesta**: Son metadatos que el servidor envía antes del contenido real.
    
- **Protocolo HTTP**: Al usar el método **HEAD**, el servidor omite el "Body" (el código HTML de la página) y solo entrega los encabezados.
    
- **Seguridad por Configuración**: En un entorno real, dejar la bandera en un header sería un fallo crítico de **Exposición de Información Sensible**.

En lugar de solo `-I`, vamos a usar los parámetros específicos para que PowerShell solo nos traiga los encabezados (**headers**), que es donde está escondida la bandera:
(curl -Method HEAD -Uri http://wily-courier.picocft.net:54918/).Headers