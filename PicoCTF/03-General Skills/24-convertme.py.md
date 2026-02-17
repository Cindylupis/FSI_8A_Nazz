### **Descripción**
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/22/convertme.py
NazaretEsquivel-picoctf@webshell:~$ python convertme.py
If 77 is in decimal base, what is it in binary base?
Answer: 01001101
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}

```

#### NOTAS
Aunque se podría usar `grep` , el comando `find` es mucho más rápido cuando ya conoces el **nombre del archivo** que buscas.

- **`find .`**: Busca a partir de donde estás parado.
    
- **`-name`**: Filtra específicamente por el nombre del archivo.