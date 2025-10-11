
## Descripción

Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).


## Solución

Inicio descargando el archivo que se nos proporciona con el comando wget. Desde las pistas se nos menciona a cargo, el cual instalaremos con el siguiente comando: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
Ingresamos al directorio en que almacenamos nuestro archivo y lo vamos a descomprimir usando el comando: `gunzip fixme1.tar.gz`. 
Luego, lo desenpaquetamos  con el comando: `tar -xvf fixme1.tar`.
Nos queda el directorio del programa, y nos cambiaremos a el con el comando cd. A partir de aquí verificamos nuestro programa con el comando: `cargo check` para compilar mas rápidamente.

Al analizar los errores que tenemos, tal cual como dice en la pista logramos ver  de aquí de que tratan los errores facilmente; por lo que abrí el archivo main.rs con el editor nano y además observé comentarios con pistas para cada error.
Es cuestión de agregar un punto y coma que falta, solucionar el ret; que debería ser return sin el ; y cambiar la forma en que imprimimos una variable de :? a {} que es la manera correcta en rust.
Guardamos y corremos el proyecto con cargo run, y obtendremos la bandera desencriptada.
`picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}`


## Notas adicionales

- Cargo es el gestor de paquetes de Rust.
- La forma correcta de instalarlo es usando rustup, el gestor de versiones de Rust.
- cargo run: correrlo
- cargo check: verificar sin compilar
- gunzip: Descomprimir
- `tar -xvf: x desempaquetar, v ver archivos lista, f indicar nombre archivo.

## Referencias

https://doc.rust-lang.org/book/ch01-03-hello-cargo.html