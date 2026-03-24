## Descripción

We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/picopico.key). Recover the flag.

## Concepto Base

Para leer tráfico cifrado (HTTPS/TLS) necesitamos una **Llave Privada** (usualmente `.key` o `.pem`). Sin ella, el contenido es ilegible.
## Solución

**Solución 1- usando terminal Webshell
```
picoCTF{nongshim.shrimp.crackers}
```

## NOTAS
### Descifrado Maestro 

Este comando fuerza a `tshark` a usar la llave en el puerto 443 (HTTPS) y vuelca el contenido en hexadecimal y texto plano.
```
tshark -r capture.pcap -o "tls.keys_list:any,443,http,picopico.key" -d tcp.port==443,tls -x | grep -A 3 "picoCTF{"

NazaretEsquivel-picoctf@webshell:~$ tshark -r capture.pcap -o "tls.keys_list:any,443,http,picopico.key" -d tcp.port==443,tls -x | grep -i "pico"
0170  6f 31 11 30 0f 06 03 55 04 0a 0c 08 50 69 63 6f   o1.0...U....Pico
0170  6f 31 11 30 0f 06 03 55 04 0a 0c 08 50 69 63 6f   o1.0...U....Pico
0170  6f 31 11 30 0f 06 03 55 04 0a 0c 08 50 69 63 6f   o1.0...U....Pico
00e0  67 3a 20 67 7a 69 70 0d 0a 50 69 63 6f 2d 46 6c   g: gzip..Pico-Fl
00f0  61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67   ag: picoCTF{nong
00e0  3a 20 67 7a 69 70 0d 0a 50 69 63 6f 2d 46 6c 61   : gzip..Pico-Fla
00f0  67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73   g: picoCTF{nongs
```

- `-o "tls.keys_list..."`: Vincula la llave al tráfico.
- `-d tcp.port==443,tls`: Fuerza la decodificación como TLS.
- `-x`: Muestra el volcado (Hex Dump) donde el texto es más visible.
- `-A 3`: Muestra 3 líneas después del hallazgo (evita que la bandera se corte).


NazaretEsquivel-picoctf@webshell:~$ tshark -r capture.pcap -o "tls.keys_list:any,443,http,picopico.key" -d tcp.port==443,tls -x | grep -i "pico"
0170  6f 31 11 30 0f 06 03 55 04 0a 0c 08 50 69 63 6f   o1.0...U....Pico
0170  6f 31 11 30 0f 06 03 55 04 0a 0c 08 50 69 63 6f   o1.0...U....Pico
0170  6f 31 11 30 0f 06 03 55 04 0a 0c 08 50 69 63 6f   o1.0...U....Pico
00e0  67 3a 20 67 7a 69 70 0d 0a 50 69 63 6f 2d 46 6c   g: gzip..Pico-Fl
00f0  61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67   ag: picoCTF{nong
00e0  3a 20 67 7a 69 70 0d 0a 50 69 63 6f 2d 46 6c 61   : gzip..Pico-Fla
00f0  67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73   g: picoCTF{nongs