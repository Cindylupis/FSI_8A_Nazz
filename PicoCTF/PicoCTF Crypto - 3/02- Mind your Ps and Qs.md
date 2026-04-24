## Descripción

In RSA, a small e value can be problematic, but what about N? Can you decrypt this?[values](https://challenge-files.picoctf.net/c_wily_courier/cf5f197ac7209b73c6ae6860baa14fd149c08b2103e619b04862f064f5e19e24/values)
## Solución

**Solución 1
```
Decrypt my super sick RSA:
c: 15341890103764929939105506004034128738090325640037083301857608662849501626260517
n: 948406957756830799684818171639547165784816468744946013083947881743680617123566349
e: 65537

from Crypto.Util.number import long_to_bytes

c = 15341890103764929939105506004034128738090325640037083301857608662849501626260517
e = 65537

p = 1891771437429478964908181306574287207137
q = 501332739776173570344039681219489434626477

print("Calculando la llave privada...")

# Calculamos el módulo n (solo para verificar)
n = p * q

# Calculamos el totient (tn) 
tn = (p - 1) * (q - 1)

# Calculamos la llave privada d
d = pow(e, -1, tn)

# Desciframos el mensaje original m 
m = pow(c, d, n)

# Convertimos los números a texto legible
flag = long_to_bytes(m).decode('utf-8', errors='ignore')

print(f"\n[+] ¡Matemática superada!")
print(f"Flag: {flag}")

Flag:{FTCocip
}19ea7cd1_do0g_0n_N_11ams

picoCTF{sma11_N_n0_g0od_1dc7ae91}


```

#### NOTAS
_"Bits are expensive, I used only a little bit over 100 to save money"_.
En el mundo real, un módulo RSA ($n$) seguro tiene **2048 o 4096 bits**. Un módulo de poco más de 100 bits es un chiste para el poder de cómputo actual. Esto significa que podemos romper el candado principal de la criptografía RSA: encontrar los números primos originales ($p$ y $q$) a partir de $n$.