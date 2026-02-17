### **Descripción**

Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ nano serpentine.py
NazaretEsquivel-picoctf@webshell:~$ ======================================
NazaretEsquivel-picoctf@webshell:~$ python3 serpentine.py
Welcome to the picoCTF webshell!
    Y
  .-^-. webshell is intended only for solving picoCTF challenges. Any
 /     \      .- ~ ~ -.lation of our terms and conditions.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ . Please do not
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'ist between
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \limited. Some limits can be
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /ut after 15 minutes.
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~r's guide, type less ~/README.txt.

Welcome to the serpentine encourager!=====================================


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) a
picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}

```

#### NOTAS
- En el bloque `if` donde el usuario elige imprimir la bandera, borra la llamada a la función incorrecta (como `print_encouragement()`).
    
- Escribe en su lugar la llamada a la función que encontraste: `print_flag()`.