
## Descripción

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090

## Solución

Ingresamos al sitio web y se nos da algo de contexto a parte de las pistas.
Ingresamos sesión como un usuario y al abrir el cookie editor vemos que se nos guarda la cookie con un token jwt con el que se reconoce la sesión.
Lo copeamos y vamos al sitio jwt.io para pegarlo y verlo decodificado, por lo que dice nuestro usuario. Si intentamos simplemente cambiar el usuario a admin y reemplazar el token codificado en la cookie veremos que esto no funcionará ya que la firma no coincide por que tiene un password.
Lo que haremos será crakear esto y para ello copeamos nuestro token y lo guardamos en un archivo.
Verificamos que tenemos el archivo rockyou y lo desempaquetamos con un gzip -d, este es el diccionario con las palabras que usaremos.
Haremos uso de la herramienta jhon con un ataque de diccionario para obtener la contraseña para firmar los token, y encontramos que es: ilovepico.
Solamente cambiamos nuestro token con el sitio jwt.io con el usuario admin y firma ilovepico, cambiamos la cookie con el nuevo token y obtendremos la bandera.

## Notas adicionales


## Referencias

[picoCTF 2019 writeup [10] - Web - JaWT Scratchpad](https://www.youtube.com/watch?v=iaKbvrbcSko&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=10)