## Descripción

A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.

Download the message [here](https://artifacts.picoctf.net/c/181/message.txt).
## Solución

**Solución 1
```
- `DF3LP3VZS` = **FR3QU3NCY** (Frequency / Frecuencia) 
- `4774ZN5` = **4774CK5** (Attacks / Ataques)  
- `4F3` = **4R3** (Are / Son)   
- `Z001` = **C001** (Cool / Geniales)   
- `4871X6DT` = **4871E6FB**
  
Flag :picoCTF{FR3QU3NCY_4774CK5_4R3_C001_4871E6FB}

```

#### NOTAS
Resolución de un cifrado de sustitución simple (Simple Substitution Cipher) mediante criptoanálisis conocido como ataque de "Known-Plaintext". Al identificar el formato de la flag (`cbzjZWD` = `picoCTF`), se dedujo el mapeo de caracteres clave para desencadenar un efecto dominó sobre el resto del mensaje sin requerir análisis de frecuencias exhaustivo