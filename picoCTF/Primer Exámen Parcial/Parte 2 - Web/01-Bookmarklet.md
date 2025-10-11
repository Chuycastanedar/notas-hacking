
## Descripción

Why search for the flag when I can make a bookmarklet to print it for me? Browse [here](http://titan.picoctf.net:49931/), and find the flag!

## Solución

Ingresamos al sitio web.
Tenemos solamente texto al centro, y lo más importante un recuadro con un fragmento de código.
Si lo analizamos veremos que es una función y tiene la bandera encriptada por lo que vamos a copear este código, damos clic derecho, inspect, nos vamos a  la consola y ejecutamos el código.
Nos abrirá una alerta, un recuadro con la bandera.
`picoCTF{p@g3_turn3r_6bbf8953}`


## Notas adicionales

- Por defecto no se nos permite ejecutar código como medida de seguridad, necesitamos escribir `allow pasting` antes de ello.

## Referencias

