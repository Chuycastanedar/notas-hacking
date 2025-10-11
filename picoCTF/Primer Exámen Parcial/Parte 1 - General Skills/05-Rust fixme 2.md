
## Descripción

The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee? Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

## Solución

Inicio descargando el archivo que se nos proporciona con el comando wget.
Lo vamos a descomprimir usando el comando: `gunzip fixme2.tar.gz`. 
Luego, lo desenpaquetamos  con el comando: `tar -xvf fixme2.tar`.
Nos queda el directorio del programa, y nos cambiaremos a el con el comando cd. 
A partir de aquí verificamos nuestro programa con el comando: `cargo check` para compilar mas rápidamente.

Nos encontraremos con una variedad de errores, uno simplemente de sintaxis en el return eliminando el ;, hasta tiene un comentario.
En cuanto a los demás errores, primero analicé el sitio que se asignó en las pistas.
Después de esto y analizar el compilador que es bastante claro, los errores se centran en que se intenta modificar un String de una variable inmutable. 
Simplemente necesitamos agregar la declaración mut junto a las referencias &, y también al declarar la variable. 
(El mismo compilador lo señala muy claro en sus ubicaciones)
Al compilar no tendremos errores y al correr observaremos un mensaje con la bandera desencriptada!.
`picoCTF{4r3_y0u_h4v1n5_fun_y31?}`


## Notas adicionales


## Referencias

https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.htmlhttps://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html