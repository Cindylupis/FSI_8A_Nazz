## Descripción

Kishor Balan tipped us off that the following code may need inspection:http://fickle-tempest.picoctf.net:65401

## Concepto: Metadatos y Honeyflags

En retos más avanzados, la bandera no siempre está en el encabezado HTTP. Puede estar en:
1. **Cuerpo del mensaje:** El contenido HTML o TXT.
2. **Metadatos de archivos:** Comentarios en imágenes, perfiles EXIF o ICC (como en este caso).
3. **Honeyflags:** Banderas falsas diseñadas para engañar a scripts automáticos.
## Solución

**Solución 1-usando terminal Webshell
```
 NazaretEsquivel-picoctf@webshell:~$ tshark -r capture.pcap -o "tls.keys_list:any,443,http,picopico.key" -d tcp.port==443,tls -x | grep "picoCTF{"
00f0  61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73   ag: picoCTF{this
00f0  67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e   g: picoCTF{this.
0070  00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b   ........picoCTF{

NazaretEsquivel-picoctf@webshell:~$ tshark -r capture.pcap -o "tls.keys_list:any,443,http,picopico.key" -d tcp.port==443,tls -x | grep -A 3 "picoCTF{"
00f0  61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73   ag: picoCTF{this
0100  2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61   .is.not.your.fla
0110  67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74   g.anymore}..Cont
0120  65 6e 74 2d 4c 65 6e 67 74 68 3a 20 38 34 37 0d   ent-Length: 847.
--
00f0  67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e   g: picoCTF{this.
0100  69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67   is.not.your.flag
0110  2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65   .anymore}..Conte
0120  6e 74 2d 4c 65 6e 67 74 68 3a 20 31 30 30 0d 0a   nt-Length: 100..
--
0070  00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b   ........picoCTF{
0080  68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65   honey.roasted.pe
0090  61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f   anuts}......ICC_
00a0  50 52 4f 46 49 4c 45 00 01 01 00 00 02 0c 6c 63   PROFILE.......lc
  
picoCTF{honey.roasted.peanuts}
```

## NOTAS
### Búsqueda con Contexto

Para evitar que la bandera se corte y para ver si hay varias opciones, usamos `-A` (After) para ver las líneas siguientes:
```
tshark -r capture.pcap -o "tls.keys_list:any,443,http,picopico.key" -d tcp.port==443,tls -x | grep -A 3 "picoCTF{"
```
### Análisis de Resultados

En este reto aparecieron dos resultados:

- **Falsa:** `picoCTF{this.is.not.your.flag.anymore}` (Ubicada en headers).
- **Real:** `picoCTF{honey.roasted.peanuts}` (Ubicada en el bloque de datos de la imagen).