
## Descripción

Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/a614a27d4cb251d04c7d2f3f3f76a965/cat.jpg)


## Solución

Inicio descargando la imagen usando el comando wget.

Abro la imagen y no encuentro nada.
De acuerdo a una de las pistas del reto que menciona que revise los detalles del archivo, uso el comando exiftool mediante el cual obtengo la info.

Observo una cadena de caracteres de letras y números en el apartado de License, la copeo y llevo a cyberchef y pruebo a desencriptarlo de base 64.

Obtengo la bandera:
`picoCTF{the_m3tadata_1s_modified}`


## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjk
