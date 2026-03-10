## Descripción

Try [here](http://titan.picoctf.net:56328/) to find the flag

## 🎯 Objetivo

Bypassear (saltarse) una verificación de autenticación de dos factores (2FA) modificando la petición HTTP en tránsito.
## Solución - Usando Burp Suite

**Solución 1
```
Welcome, tiks you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_c94b61ac}

```

#### NOTAS
- Si una página se queda cargando infinitamente mientras uso Burp, es porque el **Intercept** está activado y está esperando un "Forward".

- Eliminar parámetros es una técnica común de _Fuzzing_ o pruebas de robustez para ver cómo reacciona el backend ante datos faltantes.


- **Interceptación de Tráfico:** Uso de un Proxy (Burp Suite) para detener una petición antes de que llegue al servidor.
- **Manipulación de Parámetros:** Modificar o eliminar datos que el navegador envía al servidor (como el código OTP).
- **Validación Insuficiente:** Una vulnerabilidad donde el servidor no verifica qué sucede si un dato esperado simplemente no existe en la petición.