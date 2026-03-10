## Descripción

Alright, enough of using my own encryption. Flask session cookies should be plenty secure!http://wily-courier.picoctf.net:50886/

El objetivo aquí es "falsificar" una cookie de administrador para que el sitio nos dé la bandera.
## Solución

**Solución 1
```
Cookie:
eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aakacQ.VQ6sQ1KxBihJvD9miINo9nc9gRQ

eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aakdHw.aySbsf_fxIttcWLFFGc6ewMaSmY

```

#### NOTAS
1.Actualiza los repositorios:** `sudo apt update`
2.Instala pip (el gestor de paquetes de Python):** `sudo apt install python3-pip`
3.Ahora sí, instala flask-unsign:** `pip install flask-unsign`