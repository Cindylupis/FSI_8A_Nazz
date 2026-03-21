## Descripción

Descifra este [mensaje](https://challenge-files.picoctf.net/c_fickle_tempest/67884a117da864fd93ca3cfc5d8b4d1aae71c84d7f3d2a89c1b5d0b3a19e0a71/message.wav) de la luna.

### El Concepto: SSTV

Las misiones Apollo utilizaron una tecnología llamada **SSTV (Slow Scan Television)** para enviar imágenes desde la Luna a la Tierra. Básicamente, la imagen se convierte en una señal de audio que suena como una serie de pitidos y ruidos estáticos de diferentes frecuencias.
## Solución

**Solución 1 - Usando Online SSTV Decoder
```
https://sstv-decoder.mathieurenaud.fr/
picoCTF{beep_boop_im_in_space}
```

#### NOTAS
Conceptos Clave 
- **SSTV (Slow Scan Television):** Método de transmisión de imágenes utilizado por radioaficionados y misiones espaciales (como las Apollo) para enviar datos visuales a través de canales de audio de banda estrecha. 
- **Modos SSTV:** Existen varios modos (Scottie, Martin, Robot). Para misiones lunares se suele detectar automáticamente el modo **Scottie 1**.

