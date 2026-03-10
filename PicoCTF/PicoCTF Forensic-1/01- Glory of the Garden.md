
## Descripción

This file contains more than it seems.Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg).

### El Concepto: Esteganografía básica

A veces, los datos se ocultan al final de un archivo de imagen. Para el ojo humano y para el visor de fotos, la imagen se ve normal porque el visor ignora todo lo que está después del marcador de "Fin de Imagen". Pero un **Editor Hexadecimal** nos permite ver los bytes crudos del archivo.
## Solución

**Solución 1- Usando terminal
```
NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg
--2026-03-10 19:20:44--  https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295191 (2.2M) [application/octet-stream]
Saving to: 'garden.jpg'

garden.jpg           100%[=====================>]   2.19M  1.81MB/s    in 1.2s    

2026-03-10 19:20:45 (1.81 MB/s) - 'garden.jpg' saved [2295191/2295191]

NazaretEsquivel-picoctf@webshell:~$ strings garden.jpg | grep "picoCTF"
Here is a flag: picoCTF{more_than_m33ts_the_3y339cbe6dc}
```

#### NOTAS
**Usar el comando `strings`:** Este comando busca secuencias de caracteres imprimibles dentro de archivos binarios. Ejecuta esto:
```
strings garden.jpg | grep "picoCTF"
```