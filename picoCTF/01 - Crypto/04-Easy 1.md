
## Descripción

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

## Solución

Se nos da una tabla la cual podemos utilizar para desencriptar a mano el mensaje de acuerdo a la clave. También pudiéramos realizar un programa que lo automatice.

En este caso abrí la operación Vigenère Decode en Cyberchef, ingresé el mensaje y la llave y obtuve la bandera:
`picoCTF{CRYPTOISFUN}`

## Notas adicionales

- El **cifrado de Vigenère** es un cifrado basado en diferentes series de caracteres o letras del [cifrado César](https://es.wikipedia.org/wiki/Cifrado_C%C3%A9sar "Cifrado César") formando estos caracteres una tabla, llamada **tabla de Vigenère**, que se usa como clave.

## Referencias

https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkI

https://es.wikipedia.org/wiki/Cifrado_de_Vigen%C3%A8re