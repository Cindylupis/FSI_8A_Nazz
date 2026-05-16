## Descripción

Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).
## Solución

**Solución 1
```
usuarionazz890@DESKTOP-EHL2SJN:~$ cd /mnt/c/Users/Usuario/Downloads/fixme3/fixme3
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads/fixme3/fixme3$ nano src/main.rs
usuarionazz890@DESKTOP-EHL2SJN:/mnt/c/Users/Usuario/Downloads/fixme3/fixme3$ cargo run
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/mnt/c/Users/Usuario/Downloads/fixme3/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 5.99s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

```

#### NOTAS
Resolución de un error de sintaxis habilitando un bloque de código `unsafe`. En Rust, para desreferenciar punteros crudos o llamar funciones inseguras
(como `std::slice::from_raw_parts`), es obligatorio envolver el código dentro de un bloque `unsafe {}`. **Resumen de ejecución:** Descomentar las líneas `unsafe {` y `}` en `src/main.rs`, y ejecutar `cargo run`.