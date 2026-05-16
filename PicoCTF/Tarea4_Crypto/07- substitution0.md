## Descripción

A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?

Download the message [here](https://artifacts.picoctf.net/c/153/message.txt).
## Solución

**Solución 1
```
- `5` = 5   
- `Y` = U  
- `H` = B  
- `5` = 5   
- `7` = 7   
- `1` = 1   
- `7` = 7   
- `Y` = U   
- `7` = 7 
- `1` = 1   
- `0` = 0  
- `G` = N   
- `_` = _  
- `3` = 3  
- `I` = V 
- `0` = 0  
- `X` = L   
- `Y` = U  
- `7` = 7 
- `1` = 1 
- `0` = 0  
- `G` = N  
- `_` = _  
- `03055505` = 03055505
  
Flag :picoCTF{5UB5717U710N_3V0LU710N_03055505}

```

#### NOTAS
El alfabeto normal es: `ABCDEFGHIJKLMNOPQRSTUVWXYZ` 
El alfabeto cifrado es: `OHNFUMWSVZLXEGCPTAJDYIRKQB`