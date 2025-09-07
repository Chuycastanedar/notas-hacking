
## Descripción

Someone's commits seems to be preventing the program from working. 
Who is it?You can download the challenge files here: challenge.zip

## Solución

Iniciamos descargando el challenge.zip que se nos da usando el comando wget y el vínculo.
Ya descargado, lo descomprimimos con el comando unzip.
Podemos observar que nos genera un repositorio de git.
De acuerdo a las pistas y descripción entendemos que debemos revisar el historial de commits, por lo que apliqué un git log y me percaté que son demasiados commits.
Intenté buscar la bandera usando un git log para el historial y un grep para buscar la coindcidencia unidos por un pipe y la encontré.

``` bash
JCR_07-picoctf@webshell:~/drop-in$ git log | grep "{"
Author: picoCTF{@sk_th3_1nt3rn_2c6bf174} <ops@picoctf.com>
```

## Notas adicionales

- git log Comando para entrar al historial de commits

## Referencias
