
## Descripción

BookShelf Pico, my premium online book-reading service. I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book! Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/481/bookshelf-pico.zip). Website can be accessed [here!](http://saturn.picoctf.net:63013/).

## Solución

Iniciamos descargando el código fuente que se nos da.
Al analizarlo podemos destacar que en UserService.java aparece una autoridad Admin e nteractúa con tokens JWT, punto importante mencionado también en las pistas.

En SecretGenerator.java observamos que al generar una cadena de caracteres aleatoria, realmente no lo es y devuelve `1234`.
Ingresamos al sitio web y accedemos usando las credenciales: user, user. Abriremos las herramientas de desarrollador y nos iremos a la pestaña de Storage, donde abriremos el apartado de Local Storage y daremos con el token JWT en el cuál el rol es free.

Lo vamos a copear y nos iremos a buscar alguna página de JWT decode.
Ingresamos el token y cambiaremos el rol a Admin, email a admin y lo firmaremos con 1234; ambas cosas que sabemos de analizar el código. También el userId a 2.

Cambiamos el token por el nuevo y modificamos token-payload con los mismos datos.
Al recargar la página vamos acceder como admin, y al entrar al apartado flag nos permitirá cargar el archivo y ver la bandera.
`picoCTF{w34k_jwt_n0t_g00d_ca4d9701}`


## Notas adicionales


## Referencias

https://www.jwt.io/