## Descripción

In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding!

The source code for this vault is here: [VaultDoor5.java](https://challenge-files.picoctf.net/c_fickle_tempest/a6800ecd79ccb3d5aa6495c2686ac0120e3e3b187f13ff0a6f095981dc5dd854/VaultDoor5.java)
## Solución

**Solución 1
```

Flag :picoCTF{c0nv3rt1ng_fr0m_ba5e_64_4185551e}

```

#### NOTAS
Ingeniería inversa de doble codificación en Java, invirtiendo el orden de ejecución: decodificación Base64 seguida de decodificación URL (Percent-encoding) para recuperar el texto plano