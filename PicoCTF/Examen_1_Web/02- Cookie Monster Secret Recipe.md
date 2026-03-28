## Descripción

Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:56829/) and good luck
## Solución

**Solución 1
```
Cookie Value:
cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzQ3MzZGNkNCfQ%3D%3D

picoCTF{c00k1e_m0nster_l0ves_c00kies_4736F6C\\}

picoCTF{c00k1e_m0nster_l0ves_c00kies_4736F6CB}
```

#### NOTAS
- ### Web: Cookie Monster

- **Técnica:** Manipulación de Cookies + Base64.
- **Herramienta:** Navegador (F12) > Application > Cookies.
- **Análisis:** Los datos en cookies no están cifrados, solo codificados.
- **Fix:** `atob("valor")` en Consola para decodificar. (Cambiar `%3D` por `=` si es necesario).