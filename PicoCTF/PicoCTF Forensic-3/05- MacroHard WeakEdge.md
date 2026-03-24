## Descripción

I've hidden a flag in this file. Can you find it?[Forensics_is_fun.pptm](https://challenge-files.picoctf.net/c_wily_courier/d78815176c19ddc85a1388233268d2f4c459fcbbaab197b4a29ebafc88294c54/Forensics_is_fun.pptm)

Los archivos de Office (`.docx`, `.pptx`, `.pptm`) son en realidad **archivos ZIP disfrazados**. Dentro de ellos hay una estructura de carpetas llena de XMLs, imágenes y, en este caso, scripts.
## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ cd ppt_extraido
NazaretEsquivel-picoctf@webshell:~/ppt_extraido$ ls -R
.:
'[Content_Types].xml'   _rels   docProps   ppt

./_rels:

./docProps:
app.xml  core.xml  thumbnail.jpeg

./ppt:
_rels          presentation.xml  slideMasters  tableStyles.xml  vbaProject.bin
presProps.xml  slideLayouts      slides        theme            viewProps.xml

./ppt/_rels:
presentation.xml.rels

./ppt/slideLayouts:
_rels              slideLayout11.xml  slideLayout4.xml  slideLayout7.xml
slideLayout1.xml   slideLayout2.xml   slideLayout5.xml  slideLayout8.xml
slideLayout10.xml  slideLayout3.xml   slideLayout6.xml  slideLayout9.xml

./ppt/slideLayouts/_rels:
slideLayout1.xml.rels   slideLayout3.xml.rels  slideLayout7.xml.rels
slideLayout10.xml.rels  slideLayout4.xml.rels  slideLayout8.xml.rels
slideLayout11.xml.rels  slideLayout5.xml.rels  slideLayout9.xml.rels
slideLayout2.xml.rels   slideLayout6.xml.rels

./ppt/slideMasters:
_rels  hidden  slideMaster1.xml

./ppt/slideMasters/_rels:
slideMaster1.xml.rels

./ppt/slides:
_rels        slide18.xml  slide27.xml  slide36.xml  slide45.xml  slide54.xml
slide1.xml   slide19.xml  slide28.xml  slide37.xml  slide46.xml  slide55.xml
slide10.xml  slide2.xml   slide29.xml  slide38.xml  slide47.xml  slide56.xml
slide11.xml  slide20.xml  slide3.xml   slide39.xml  slide48.xml  slide57.xml
slide12.xml  slide21.xml  slide30.xml  slide4.xml   slide49.xml  slide58.xml
slide13.xml  slide22.xml  slide31.xml  slide40.xml  slide5.xml   slide6.xml
slide14.xml  slide23.xml  slide32.xml  slide41.xml  slide50.xml  slide7.xml
slide15.xml  slide24.xml  slide33.xml  slide42.xml  slide51.xml  slide8.xml
slide16.xml  slide25.xml  slide34.xml  slide43.xml  slide52.xml  slide9.xml
slide17.xml  slide26.xml  slide35.xml  slide44.xml  slide53.xml

./ppt/slides/_rels:
slide1.xml.rels   slide23.xml.rels  slide37.xml.rels  slide50.xml.rels
slide10.xml.rels  slide24.xml.rels  slide38.xml.rels  slide51.xml.rels
slide11.xml.rels  slide25.xml.rels  slide39.xml.rels  slide52.xml.rels
slide12.xml.rels  slide26.xml.rels  slide4.xml.rels   slide53.xml.rels
slide13.xml.rels  slide27.xml.rels  slide40.xml.rels  slide54.xml.rels
slide14.xml.rels  slide28.xml.rels  slide41.xml.rels  slide55.xml.rels
slide15.xml.rels  slide29.xml.rels  slide42.xml.rels  slide56.xml.rels
slide16.xml.rels  slide3.xml.rels   slide43.xml.rels  slide57.xml.rels
slide17.xml.rels  slide30.xml.rels  slide44.xml.rels  slide58.xml.rels
slide18.xml.rels  slide31.xml.rels  slide45.xml.rels  slide6.xml.rels
slide19.xml.rels  slide32.xml.rels  slide46.xml.rels  slide7.xml.rels
slide2.xml.rels   slide33.xml.rels  slide47.xml.rels  slide8.xml.rels
slide20.xml.rels  slide34.xml.rels  slide48.xml.rels  slide9.xml.rels
slide21.xml.rels  slide35.xml.rels  slide49.xml.rels
slide22.xml.rels  slide36.xml.rels  slide5.xml.rels

./ppt/theme:
theme1.xml
NazaretEsquivel-picoctf@webshell:~/ppt_extraido$ cat ppt/slideMasters/hidden
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f QNazaretEsquivel-picoctf@webshell:~/ppt_extraido$ cat ppt/slideMaste64 -ddden | base6
base64: invalid input
NazaretEsquivel-picoctf@webshell:~/ppt_extraido$ cat ppt/slideMasters/hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input
NazaretEsquivel-picoctf@webshell:~/ppt_extraido$ 

 picoCTF{D1d_u_kn0w_ppts_r_z1p5}
  

```

## NOTAS
Si `base64 -d` te da error, limpia la cadena primero:
```
cat ppt/slideMasters/hidden | tr -d ' ' | base64 -d
```
- `tr -d ' '`: Borra todos los espacios en blanco.
- `base64 -d`: Decodifica la cadena limpia.

Cuando un archivo de Office tenga macros (`.pptm`), siempre revisa la carpeta `ppt/slideMasters/` y `ppt/vbaProject.bin`. Son los escondites favoritos.