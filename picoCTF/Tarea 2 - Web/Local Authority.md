
## Descripción

Can you get the flag?Go to this [website](http://saturn.picoctf.net:59410/) and see what you can discover.

## Solución

Ingreso al sitio web y me encuentro con un apartado para iniciar sesión. Pruebo a iniciar con algunos datos y solamente no funciona.
Inspecciono el código de la página y no encuentro nada muy importante, así que abro mi inspector en el apartado de network y pruebo otro inicio de sesión por lo que se me interceptan 3 métodos donde uno de ellos se encarga de los datos que ingresé a un .php y otro dice .js.
Al seleccionar el de Js e irnos a la pestaña response nos encontraremos en la lógica que evalúa el inicio de sesión donde vemos que tenemos que se evalúa a una cuenta de admin con determinada contraseña.
Simplemente tomo estos datos y vulevo a iniciar sesión con ellos y aparece la bandera.

`picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}`

## Notas adicionales


## Referencias