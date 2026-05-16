## Descripción

The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?

Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).
## Solución

**Solución 1
```
usuarionazz890@DESKTOP-EHL2SJN:~$ cd /mnt/c/Users/Usuario/Downloads/fixme2/fixme2
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads/fixme2/fixme2$ ls
Cargo.lock  Cargo.toml  src
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads/fixme2/fixme2$ nano src/main.rs
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads/fixme2/fixme2$ cargo run
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/mnt/c/Users/Usuario/Downloads/fixme2/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 5.94s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}

picoCTF{4r3_y0u_h4v1n5_fun_y31?}

```

#### NOTAS
Reparación de un error de compilación por reglas de _Borrowing_ en Rust, agregando permisos de mutabilidad (`let mut` y `&mut`) a una variable pasada por referencia. **Resumen de comandos:** `cd [ruta_del_proyecto]` > `nano src/main.rs` (agregar `mut` en la declaración, llamada y función) > `cargo run` para compilar y capturar la flag.