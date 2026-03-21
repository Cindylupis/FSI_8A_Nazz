## Descripción

Solve the quiz.Download the source code to answer questions [here](https://challenge-files.picoctf.net/c_lonely_island/e5fbf0e17f23165626b00e48e108e9bde981e528ad0fa178051d8299cdeaa42b/vuln.c).Download the binary to answer questions [here](https://challenge-files.picoctf.net/c_lonely_island/e5fbf0e17f23165626b00e48e108e9bde981e528ad0fa178051d8299cdeaa42b/vuln).Connect with the challenge instance here: `nc lonely-island.picoctf.net 63311`

## Solución

**Solución 1 - Usando terminal WebShell
```
NazaretEsquivel-picoctf@webshell:~$ nm exploit_debug | grep win
08049196 T win


[*] Question number 0x1:

Is this a '32-bit' or '64-bit' ELF? (e.g. 100-bit)

💡 Hint: Check if the system is x86_64 or x86. No compilation flag specified means default.

>> 64-bit


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x2:

What's the linking of the binary? (e.g. static, dynamic)

💡 Hint: The program uses standard library functions like fprintf, fgets, and system.

>> dynamically linked


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0x2:

What's the linking of the binary? (e.g. static, dynamic)

💡 Hint: The program uses standard library functions like fprintf, fgets, and system.

>> dynamic


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x3:

Is the binary 'stripped' or 'not stripped'?

💡 Hint: By default, binaries compiled without the -s flag contain debugging symbols.

>> no stripped


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0x3:

Is the binary 'stripped' or 'not stripped'?

💡 Hint: By default, binaries compiled without the -s flag contain debugging symbols.

>> not


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0x3:

Is the binary 'stripped' or 'not stripped'?

💡 Hint: By default, binaries compiled without the -s flag contain debugging symbols.

>> not stripped


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x4:

Looking at the vuln() function, what is the size of the buffer in bytes? (e.g. 0x10)

💡 Hint: Check the declaration in the function and answer in either hex or decimal

>> 0x15


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x5:

How many bytes are read into the buffer? (e.g. 0x10)

💡 Hint: Check the fgets

>> 0x90


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x6:

Is there a buffer overflow vulnerability? (yes/no)

💡 Hint: Compare buffer size and input size

>> yes


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x7:

Name a standard C function that could cause a buffer overflow in the provided C code.

💡 Hint: (e.g. fprintf)

>> fgets


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x8:

What is the name of function which is not called any where in the program?

💡 Hint: Analyze the source

>> win


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0x9:

What type of attack could exploit this vulnerability? (e.g. format string, buffer overflow, etc.)

💡 Hint: Try interpreting the information gathered so far

>> buffer overflow


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0xa:

How many bytes of overflow are possible? (e.g. 0x10)

💡 Hint: Subtract values

>> 0x7b


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0xb:

What protection is enabled in this binary?

💡 Hint: Learn to use checksec

>> PIE


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xb:

What protection is enabled in this binary?

💡 Hint: Learn to use checksec

>> NX


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0xc:

What exploitation technique could bypass NX? (e.g. shellcode, ROP, format string)

💡 Hint: Choose from the options

>> ROP 


✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 
✅                    ✅
✅      Correct!      ✅
✅                    ✅
✅ ✅ ✅ ✅ ✅ ✅ ✅ ✅ 


[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address

>> 0x08049196


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address

>> 0x8049196


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address

>> 0x8049196


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address

>> 0x08049196


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address

>> 



🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address

>> 


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address

>> 

🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 
🔥                    🔥
🔥       Wrong!       🔥
🔥                    🔥
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 


❌ Incorrect. Try again!

[*] Question number 0xd:

What is the address of 'win()' in hex? (e.g. 0x4011eb)

💡 Hint: Use gdb/objdump to find the address
```

#### NOTAS
Resolución 
1. **Conexión Remota:** Se utilizó `netcat` desde la Web Shell de picoCTF para establecer un socket TCP. `nc candy-mountain.picoctf.net 64694` 
2. **Desafío del Servidor:** El programa solicitó una secuencia de bytes basada en valores decimales ASCII (101, 101, 101). 
3. **Conversión:** - Valor Decimal 101 = Carácter 'e' (ASCII). - Cadena requerida: "eee". 
4. **Resultado:** Al enviar la cadena, el servidor validó la entrada y liberó el buffer que contenía la bandera.