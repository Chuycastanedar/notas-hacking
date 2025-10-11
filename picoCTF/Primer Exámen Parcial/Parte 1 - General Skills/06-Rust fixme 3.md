
## Descripción

Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).

## Solución

Inicio descargando el archivo que se nos proporciona con el comando wget.
Lo vamos a descomprimir usando el comando: `gunzip fixme2.tar.gz`. 
Luego, lo desenpaquetamos  con el comando: `tar -xvf fixme2.tar`.
Nos queda el directorio del programa, y nos cambiaremos a el con el comando cd. A partir de aquí verificamos nuestro programa con el comando: `cargo check` para compilar mas rápidamente.
Me encuentro con varios errores, pero en las pistas se que debo checar los comentarios por lo que abro mi archivo main.rs con un editor como pluma y me encuentro con un par de pistas y un enlace al que entro y analizo.
Las pistas y el sitio hablan de unsafe, una instrucción que podemos usar en rust para abrir un bloque de código que obtiene acceso a forzar una serie de acciones que normalmente están prohibidas o que el compilador no permitiría y nos daría error. 
Comprendido esto, volví a analizar el código y me di cuenta que ya contaba con un bloque unsafe simplemente que estaba comentado, por lo que eliminé los // para que dejara de estar comentado, compilé y al correr el programa funcionó y me entregó la bandera.
`picoCTF{n0w_y0uv3_f1x3d_1h3m_411}`


## Notas adicionales

- Unsafe es una puerta de escape que te permite romper algunas reglas de rust bajo tu propia responsabilidad.
- No desactiva la seguridad, solo te da acceso a ¨superpoderes¨ para tareas de bajo nivel. 
- La clave es mantener los bloques unsafe lo más pequenos y justificados posible.
- A veces el código es seguro pero el compilador no tiene suficiente información para garantizarlo y lo rechaza. Unsafe permite forzarlo.


## Referencias

https://doc.rust-lang.org/book/ch20-01-unsafe-rust.html