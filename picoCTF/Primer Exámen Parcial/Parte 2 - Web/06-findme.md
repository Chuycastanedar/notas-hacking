
## Descripción

Help us test the form by submiting the username as `test` and password as `test!` The website running [here](http://saturn.picoctf.net:61387/).

## Solución

Ingresamos al sitio web que se nos da.
Entramos con el usuario y password que se nos menciona: test y test!.
Damos dos veces clic en la flecha de retroceso de la página y copeamos la cadena de caracteres a partir de un id= que hay a mitad del url. Damos ahora un clic de en la flecha pero de siguiente ahora y también copeamos la cadena a partir de la parte id=.

Ambas cadenas de caracteres ls llevamos a cyberchef y usamos la conversión from base 64. Obtendremos la bandera.
`picoCTF{proxies_all_the_way_3d9e3697}`

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnR3Y205NGFXVnpYMkZzYkY5MGFHVmZkMkY1WHpOa09XVXpOamszZlE9PQ