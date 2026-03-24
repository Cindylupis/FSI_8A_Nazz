## Descripción

We found this file. Recover the flag.[tunn3l_v1s10n](https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n)

Básicamente, el archivo está dañado a propósito para que la computadora no sepa qué es.
## Solución

**Solución 1- usando LINUX
```
usuarionazz890@DESKTOP-EHL2SJN:~$ cd /mnt/c/Users/Usuario/Downloads
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads$ wget https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n
--2026-03-24 13:20:29--  https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.115, 18.238.132.49, 18.238.132.88, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: ‘tunn3l_v1s10n’

tunn3l_v1s10n                 100%[=================================================>]   2.76M  2.47MB/s    in 1.1s

2026-03-24 13:20:34 (2.47 MB/s) - ‘tunn3l_v1s10n’ saved [2893454/2893454]

usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads$ python3 -c "f=open('tunn3l_v1s10n','r+b'); f.seek(10); f.write(b'\x36\x00\x00\x00'); f.close()"
python3 -c "f=open('tunn3l_v1s10n','r+b'); f.seek(14); f.write(b'\x28\x00\x00\x00'); f.close()"
python3 -c "f=open('tunn3l_v1s10n','r+b'); f.seek(22); f.write(b'\x52\x03\x00\x00'); f.close()"
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads$ mv tunn3l_v1s10n bandera_revelada.bmp

 picoCTF{qu1t3_a_v13w_2020}
  

```
![[bandera_revelada.bmp|313]]
## NOTAS
## El Secreto del "Túnel"

El archivo tiene datos de píxeles que el visor de Windows ignora porque la cabecera dice que la imagen es más pequeña de lo que realmente es. Al aumentar la **altura (height)**, "forzamos" al visor a mostrar la parte oculta.

## Comandos de Reparación Local

Si estás en la carpeta de Windows desde WSL (`/mnt/c/Users/...`):
1. Corregir inicio de datos (Offset 10)
python3 -c "f=open('tunn3l_v1s10n','r+b'); f.seek(10); f.write(b'\x36\x00\x00\x00'); f.close()"
2. Corregir tamaño de cabecera DIB (Offset 14)
python3 -c "f=open('tunn3l_v1s10n','r+b'); f.seek(14); f.write(b'\x28\x00\x00\x00'); f.close()"
3. Revelar bandera aumentando altura (Offset 22)
python3 -c "f=open('tunn3l_v1s10n','r+b'); f.seek(22); f.write(b'\x52\x03\x00\x00'); f.close()"