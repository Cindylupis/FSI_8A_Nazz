## Descripción

Why use p and q when I can use more?Connect with nc fickle-tempest.picoctf.net 51039.

**Solución 1
```
from Crypto.Util.number import long_to_bytes

c = 11680838573511200373428936340299811771876780554622236220642254910589279201763843430057271891552496393054032949870674036238655209993282964758211416675830194668159084143919511032168843986630115610828570024694736950958531580791481501896597492698318576737433332320572525077658378761537809841563097096918187155238444106733183467488872092035956521074
n = 14251132361786006289730369410691060792566513607464771494440121567592372795639223786053680468745216471017605249118155174919660447780118776021384173150392728216097443002865779974304203840341683535890479218810559528739876656363396691312240116545720450997663562195951185452392909872459507969240482018566254401177567064503610252285939215431405947757
e = 65537

# Tus 34 primos limpiecitos
factores = [
    8915758837,
    9135216319,
    9559355807,
    9758759783,
    9959018737,
    10489987283,
    10560719293,
    10708472167,
    11172500831,
    11250386269,
    11281047881,
    11517882043,
    11601495047,
    12043678211,
    12261298813,
    12507778099,
    12634194379,
    12690373457,
    12743491759,
    13203474017,
    13342837357,
    13490737861,
    13722000841,
    14099148599,
    14173868867,
    14242989251,
    14343458771,
    14386506287,
    14639160191,
    14728029619,
    14810738629,
    15010469839,
    15245877067,
    15861013967
]

print("Verificando factores...")
producto = 1

for f in factores:
    producto *= f

if producto != n:
    print("\n[!] ¡ALTO AHÍ! La multiplicación de los factores NO es igual a 'n'.")
    exit()
else:
    print("[+] Los factores coinciden con el módulo n. ¡Todo al cien!")

print("Calculando el totient (multi-primo)...")
tn = 1
for f in factores:
    tn = tn * (f - 1)

d = pow(e, -1, tn)
m = pow(c, d, n)

bytes_crudos = long_to_bytes(m)
flag = bytes_crudos.decode('utf-8', errors='ignore')

print(f"\n[+] ¡Reto destrozado!")
print(f"Flag: {flag}")


Flag: picoCTF{too_many_fact0rs_3023548}


```

#### NOTAS
El único "truco" para descifrar esto es que el cálculo del _totient_ ($\phi$) cambia. En lugar de ser solo $(p-1)(q-1)$, tienes que restarle 1 a **cada uno** de los primos que encuentres y multiplicarlos todos juntos:

$$tn = (p-1)(q-1)(r-1)\dots$$

Una vez que tienes ese nuevo $tn$, el resto del ataque es idéntico: sacas $d$ y descifras.