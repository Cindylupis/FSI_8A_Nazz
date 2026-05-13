## Descripción

This vault uses ASCII encoding for the password.

The source code for this vault is here: [VaultDoor4.java](https://challenge-files.picoctf.net/c_fickle_tempest/5a242afc9022df976b1c18fe9364788579431217536fca41006714b29d8931e1/VaultDoor4.java)
## Solución

**Solución 1
```

Flag :picoCTF{jU5t_4_bUnCh_0f_bYt3s_ 30dc85bed}

```

#### NOTAS
Decodificación de un array de bytes ofuscado en múltiples bases numéricas integradas en Java: Decimal (sin prefijo), Hexadecimal (prefijo `0x`) y Octal (prefijo `0`), traducidas a caracteres ASCII.