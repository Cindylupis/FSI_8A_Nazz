## Descripción

Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.

`ssh -p 55018 ctf-player@saturn.picoctf.net`. The password is `3f39b042`
## Solución

**Solución 1
```
Specialer$ read linea < ala/kazam.txt
Specialer$ echo $linea
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_811ae7e9}

picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_811ae7e9}

```

#### NOTAS
Evasión de una _Python Restricted Shell_ donde `cat` está en lista negra, utilizando el comando integrado de Bash `read linea < archivo` para volcar el contenido. **Solución:** Se leyó directamente el archivo `ala/kazam.txt` para extraer la flag saltándose las restricciones del entorno sin invocar binarios externos.