## Descripción

A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it?

Download the message [here](https://artifacts.picoctf.net/c/188/message.txt).

Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.
## Solución

**Solución 1
```
Nivel 1: T . . . . . a . . . . .   . . . . . _
Nivel 2: . h . . . l . g . . . : . W . . . 3 .
Nivel 3: . . e . f . . .   . s . . . H . R . .
Nivel 4: . . .   . . . . . i . . . . . 3 . . .

The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997

Flag :picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997}

```

#### NOTAS
### ¿Cómo funciona el Rail Fence Cipher?

El remitente escribe el mensaje en un patrón de zigzag subiendo y bajando a través de un número específico de "rieles" (líneas). Luego, para cifrarlo, lee el texto fila por fila de izquierda a derecha.