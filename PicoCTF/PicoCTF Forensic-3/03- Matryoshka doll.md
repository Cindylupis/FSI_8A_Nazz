## Descripción

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one?Image: [dolls.jpg](https://challenge-files.picoctf.net/c_wily_courier/e211d20af86cc82c4622e672d634045f31ec3901d7aa4714393fa9db2d9a3cd3/dolls.jpg)
## Solución

**Solución 1- 
```
 picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}
  
```

## NOTAS
**Proceso de Extracción Recursiva:**

1. Identificar archivo sospechoso con `ls`.
2. Extraer con `binwalk -e [archivo]`.
3. Entrar a la carpeta `_[archivo].extracted`.
4. Navegar por las subcarpetas creadas hasta repetir el ciclo.

**Tip de eficiencia:** En retos de muchas capas, puedes usar `find . -name "*.txt"` para buscar el archivo final sin tener que navegar manualmente por cada carpeta `base_images`.