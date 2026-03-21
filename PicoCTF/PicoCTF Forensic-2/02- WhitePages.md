## Descripción

I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/a8c97e66798b74645b536e392d4374d015529f1e9a812f5a68ed943dc4719e09/whitepages.txt) is all blank!

## Hipótesis##
El archivo utiliza el lenguaje **Whitespace** o una codificación binaria personalizada donde un tipo de espacio representa un `0` y el otro un `1`.

**Solución 1 - Usando terminal WSL
```
picoCTF{not_all_spaces_are_created_equal_57203502a1f295faf0d8cf42a1d4c769}
```

#### NOTAS
**Esteganografía en texto:** No todo archivo "vacío" carece de información; los caracteres invisibles son vectores comunes para ocultar datos.

### Resolución

1. Para decodificar el mensaje, se creó un script en Python (`solucion.py`)
```
# Abrimos el archivo en modo binario
with open('whitepages.txt', 'rb') as f:
    data = f.read()

# Sustituimos los patrones invisibles por binario
# NOTA: Asegúrate de que el nombre del archivo coincida arriba
binary = data.replace(b'\xe2\x80\x83', b'0').replace(b'\x20', b'1')

# Convertimos de binario a texto ASCII
def decode_binary(binary_str):
    msg = ""
    for i in range(0, len(binary_str), 8):
        byte = binary_str[i:i+8]
        msg += chr(int(byte, 2))
    return msg

print(decode_binary(binary.decode()))
```
3. Se ejecutó el intérprete:
```
python3 solucion.py
```

