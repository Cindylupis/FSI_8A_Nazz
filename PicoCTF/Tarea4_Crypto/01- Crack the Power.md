## Descripción

We received an encrypted message. The modulus is built from primes large enough that factoring them isn’t an option, at least not today. See if you can make sense of the numbers and reveal the flag.

Download the [message](https://challenge-files.picoctf.net/c_amiable_citadel/dffd15f730cc296fcbf77d81509599bd677bdfedfa6b99f704c3e24b0949a460/message.txt).
## Solución

**Solución 1
```
¡La flag encontrada es:
picoCTF{t1ny_e_af0d7666}
```

#### NOTAS
Explotación de vulnerabilidad en RSA con exponente pequeño ($e=20$) y mensaje corto ($m^e < n$), permitiendo recuperar el texto plano al calcular la raíz entera exacta (raíz vigésima mediante búsqueda binaria) sin necesidad de factorizar el módulo $n$