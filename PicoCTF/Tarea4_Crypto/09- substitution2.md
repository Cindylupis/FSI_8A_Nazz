## Descripción

It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher?

Download the message [here](https://artifacts.picoctf.net/c/113/message.txt).
## Solución

**Solución 1
```
- `K6F4G` -> N6R4M(NGRAM)  
- `4K41R515` -> 4N41Y515(ANALYSIS)  
- `15` -> 15(IS)  
- `73A10B5` -> 73D10U5(TEDIOUS) 
- `702E03EU` -> 702F03FC
  
Flag :picoCTF{N6R4M_4N41Y515_15_73D10U5_702F03FC}

```

#### NOTAS
Resolución de un cifrado de sustitución simple (Simple Substitution Cipher) sin espacios ni puntuación. Se resolvió mediante un ataque de texto conocido (_Known-Plaintext_) apuntando al formato de la flag, combinado con análisis de frecuencia de N-gramas (identificando subsecuencias comunes como "the") para reconstruir el mapeo