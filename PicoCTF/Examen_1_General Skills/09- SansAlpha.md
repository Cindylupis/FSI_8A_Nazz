## Descripción

The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.

`ssh -p 58096 ctf-player@mimas.picoctf.net`

Use password: `1ad5be0d`
## Solución

**Solución 1
```
SansAlpha$ /???/???[!_]64 ??????/????.???
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV83NzVhYzEyZH0=

picoCTF{7h15_mu171v3r53_15_m4dn355_775ac12d}

```

#### NOTAS
Evasión de un _bash jail_ sin usar letras, utilizando `/???/???[!_]64` para invocar `/bin/base64` de forma quirúrgica y evadir colisiones de binarios en el servidor. **Extracción:** Se aplicó el filtro sobre `??????/????.???` (`blargh/flag.txt`) para obtener el string codificado y descifrar la flag limpiamente desde la terminal local.