## Descripción

This service provides you an encrypted flag. Can you decrypt it with just N & e?

Connect to the program with netcat:

`$ nc verbal-sleep.picoctf.net 51699`

The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_verbal_sleep/32d7f9da267fbc80629d78138372a9bdf1b8e574080294e184f95878950065d2/encrypt.py).
## Solución

**Solución 1
```
┌──(kali㉿kali)-[~]
└─$ python3 solve_rsa.py
[*] Obteniendo la primera muestra...
[*] Conectando a verbal-sleep.picoctf.net:51699...
[+] Opening connection to verbal-sleep.picoctf.net on port 51699: Done
[*] Closed connection to verbal-sleep.picoctf.net port 51699
[*] Obteniendo la segunda muestra...
[*] Conectando a verbal-sleep.picoctf.net:51699...
[+] Opening connection to verbal-sleep.picoctf.net on port 51699: Done
[*] Closed connection to verbal-sleep.picoctf.net port 51699
[*] Calculando el Máximo Común Divisor (GCD)...
[+] ¡Éxito! Primo en común (p) encontrado.

[+] La flag es:
picoCTF{tw0_1$_pr!m3de643ad5}

```

#### NOTAS
Explotación de RSA mediante un ataque de Factor Común (GCD); conectándose al servidor múltiples veces para capturar diferentes módulos ($N_1$, $N_2$) que comparten un número primo debido a una mala generación de aleatoriedad, permitiendo factorizar $N$ y calcular la llave privada