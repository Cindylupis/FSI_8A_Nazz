## Descripción

If you want to hash with the best, beat this test!`nc saturn.picoctf.net 54711`
## Solución

**Solución 1
```
usuarionazz890@DESKTOP-EHL2SJN:~$ nano solve.py
  |
  |
  v
from pwn import *
import hashlib

# Conectamos al servidor
r = remote('saturn.picoctf.net', 54711)

def get_hash(text):
    return hashlib.md5(text.encode()).hexdigest()

while True:
    try:
        # Leemos hasta que nos pida el hash
        line = r.recvline().decode()
        if "picoCTF{" in line:
            print(f"¡FLAG ENCONTRADA!: {line}")
            break
        
        if "quotes:" in line:
            # Extraemos el texto entre comillas simples
            target = line.split("'")[1]
            print(f"Calculando hash para: {target}")
            
            # Enviamos la respuesta
            r.sendlineafter(b"Answer:", get_hash(target).encode())
            print(f"Enviado: {get_hash(target)}")
            
    except EOFError:
        break

r.interactive()
  
usuarionazz890@DESKTOP-EHL2SJN:~$ python3 solve.py
[+] Opening connection to saturn.picoctf.net on port 54711: Done
Calculando hash para: Babe Ruth
Enviado: 3875acc0c1561d949c39685e96b9a4bb
Calculando hash para: Australian outback
Enviado: fd14ff832f06adcdf5bb606ba606253a
Calculando hash para: a morgue
Enviado: 1c5d1684ae8cd2f62a070044e5fc40c7
¡FLAG ENCONTRADA!: picoCTF{4ppl1c4710n_r3c31v3d_3eb82b73}

[*] Switching to interactive mode
[*] Got EOF while reading in interactive
$

picoCTF{4ppl1c4710n_r3c31v3d_3eb82b73}
```

#### NOTAS
- **Problema:** Retos con temporizadores (Time-based challenges).
- **Herramienta:** `Pwntools` es la librería estándar para interactuar con servicios por red.