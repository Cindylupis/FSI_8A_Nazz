## Descripción

Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
## Solución

**Solución 1
```

usuarionazz890@DESKTOP-EHL2SJN:~/fixme1$ nano src/main.rs
  |
  |
  v
  use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS"); // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", ">

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        panic!("Error al crear el cryptor: {:?}", res.err());
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        ":?{}", // How do we print out a variable in the println function?
        String::from_utf8_lossy(&decrypted_buffer)
        
        
usuarionazz890@DESKTOP-EHL2SJN:~/fixme1$ cargo run
   Compiling rust_proj v0.1.0 (/home/usuarionazz890/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.44s
     Running `target/debug/rust_proj`
:?picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```

#### NOTAS
- **Firma del Main:** `fn main()` por defecto espera devolver `()`. Si intentas devolver un `Result`, los tipos no coinciden.
- **Panic! vs Return:** En scripts de utilidad o retos de CTF, es mejor usar `panic!` o `expect()` para manejar errores fatales de forma rápida.
- **Unwrap:** Solo es seguro llamar a `.unwrap()` si ya comprobaste con un `if` que el resultado no es un error.