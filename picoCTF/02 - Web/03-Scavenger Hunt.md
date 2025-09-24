
## Descripción

There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:44070/). Can you find it?

## Solución

Ingresamos al sitio y no encontramos mucho solo dice que se hizo con html, css y JS, inspeccionamos el código y en un comentario en el html ya encontramos la primera parte de la bandera.
Nos movemos a una hoja de css de ahí mismo y encontramos la segunda parte.
Al entrar al de JS solo nos da una pista sobre la cual ya vimos en un reto anterior por lo que ingresamos al archivo robots.txt y obtenemos otra parte.
Tenemos otra pista y damos con el archivo .htaccess que se ingresa de la misma forma y obtenemos otra parte.
Por ultimo en .DS_Store de igual manera y obtenemos la bandera completa.

## Notas adicionales

- No es posible acceder a esto siempre

## Referencias

[picoCTF 2021 writeup [13] - Web - Scavenger Hunt](https://www.youtube.com/watch?v=E2gN3AGHirc&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=13)