### **Descripción**
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

## Solución

**Solución 1- usando python**
``` 
NazaretEsquivel-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2026-02-17 05:38:53--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.77, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py.1'

runme.py.1           100%[=====================>]     270  --.-KB/s    in 0s      

2026-02-17 05:38:53 (19.6 MB/s) - 'runme.py.1' saved [270/270]

NazaretEsquivel-picoctf@webshell:~$ python3 runme.py.1
picoCTF{run_s4n1ty_run}

```

#### NOTAS
