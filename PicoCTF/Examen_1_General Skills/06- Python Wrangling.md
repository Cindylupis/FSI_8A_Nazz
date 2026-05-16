## Descripción

Python scripts are invoked kind of like programs in the Terminal...

Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/0af80634c4b5f2dc40a20b1e0808ddef0fb3b730764a045e7cd2f94910ba0c09/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/0af80634c4b5f2dc40a20b1e0808ddef0fb3b730764a045e7cd2f94910ba0c09/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/0af80634c4b5f2dc40a20b1e0808ddef0fb3b730764a045e7cd2f94910ba0c09/flag.txt.en)?
## Solución

**Solución 1
```
usuarionazz890@DESKTOP-EHL2SJN:~$ python3 ende.py -d flag.txt.en 720b6ad346f84cd483c60c7464dd95d4
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

```

#### NOTAS
Uso de un script de Python (`ende.py`) para descifrar un archivo con criptografía simétrica (Fernet) ingresando la contraseña directamente como argumento por línea de comandos. **Resumen de comandos:** `python3 ende.py -d flag.txt.en 720b6ad346f84cd483c60c7464dd95d4` para evadir el prompt interactivo y capturar la flag en pantalla.