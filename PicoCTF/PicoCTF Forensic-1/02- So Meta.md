## Descripción

Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/8e74516a5167183bf254f082a836fe7b925c25d6899feeffb68f78b1549a1224/pico_img.png).

Los metadatos son "datos sobre los datos". Por ejemplo, una foto no solo tiene píxeles; también guarda información sobre qué cámara se usó, la fecha, las coordenadas GPS o el autor. En este reto, la bandera está escondida en esos campos invisibles.
## Solución

**Solución 1
```
NazaretEsquivel-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/8e74516a5167183bf254f082a836fe7b925c25d6899feeffb68f78b1549a1224/pico_img.png
--2026-03-10 19:23:40--  https://challenge-files.picoctf.net/c_fickle_tempest/8e74516a5167183bf254f082a836fe7b925c25d6899feeffb68f78b1549a1224/pico_img.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.18, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: 'pico_img.png'

pico_img.png         100%[=====================>] 106.25K  --.-KB/s    in 0.05s   

2026-03-10 19:23:40 (1.90 MB/s) - 'pico_img.png' saved [108795/108795]

NazaretEsquivel-picoctf@webshell:~$ exiftool pico_img.png
ExifTool Version Number         : 12.40
File Name                       : pico_img.png
Directory                       : .
File Size                       : 106 KiB
File Modification Date/Time     : 2025:11:21 19:10:56+00:00
File Access Date/Time           : 2026:03:10 19:23:40+00:00
File Inode Change Date/Time     : 2026:03:10 19:23:40+00:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : picoCTF{s0_m3ta_9a8b5aa1}
Image Size                      : 600x600
Megapixels                      : 0.360

```

#### NOTAS
## Procedimiento

- **Herramienta principal:** `exiftool`. Es la utilidad más completa para leer y escribir metadatos en casi cualquier formato de archivo.
- **Comando:** `exiftool [archivo]`.
- **Hallazgo:** La flag se encontraba en un campo de metadatos (comúnmente el campo `Artist` o `Comment`).