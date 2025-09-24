
## Descripción

Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:15931/](http://mercury.picoctf.net:15931/)


## Solución

Ingresamos al link que se nos da y observamos una pagina con dos simples botones que hacen que el fondo cambie del color que dice ahí.
Si analizamos el código html veremos que tenemos los dos botones que mandan la selección al index php a través de un método get, el otro usando un método post.
Si vamos al inspector en el apartado de red y damos clic vemos como se utilizan ambos métodos, si modificamos sus solicitudes en la opción resend y seleccionamos un HEAD, al enviarlo encontraremos la bandera en la respuesta en el encabezado.


## Notas adicionales

- Podemos solucionarlo también en la terminal con un curl -I [link]


## Referencias

[picoCTF 2021 writeup [11] - Web - GET aHEAD](https://www.youtube.com/watch?v=oiZk0tIkR48&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=11)