## Descripción

Check the admin scratchpad!http://fickle-tempest.picoctf.net:55970

El objetivo es entrar al **"admin scratchpad"**
La meta es convencer al servidor de que eres el usuario `admin`.
## Solución

**Solución 1

```
Cookie Value
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiWXVwaXMifQ.cAZEnKRGm1Nm8II1HdJn_SJPKAVJnyCQtkyJ8qZPWYM



```

#### NOTAS
¿Qué es un JWT?

Es un estándar para pasar información de identidad entre un cliente y un servidor de forma segura. Se compone de tres partes separadas por puntos: `Header.Payload.Signature`.

- **Header:** Indica el algoritmo de cifrado.
- **Payload:** Contiene los datos del usuario (como el `user`).
- **Signature:** Verifica que el token no haya sido alterado.

- **Header:** Indica el algoritmo (probablemente `HS256`).
- **Payload:** Aquí verás tu nombre de usuario: `{"user": "Yupis"}`.
- **Signature:** Esta es la parte que valida que el token no ha sido alterado.