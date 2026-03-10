## Descripción

We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap). Recover the flag.

En este reto dan un archivo `.pcap`. Imaginando que es una "grabación" de todo lo que pasó por un cable de red en un momento dado. Tu misión es encontrar la conversación donde se envió la flag.
## Solución

**Solución 1
```
picoCTF{StaT31355_636f6e6e}

```

#### NOTAS
- **UDP vs TCP:** UDP no tiene control de errores ni de orden de llegada, por lo que es común ver datos "sueltos" en este protocolo en retos de CTF.
- **Filtros rápidos:** Si el archivo es muy grande, se puede usar el filtro `udp` o `ip.addr == [IP_SOSPCHOSA]` en la barra superior para limpiar el ruido.