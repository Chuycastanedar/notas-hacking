
## Descripción

This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.


## Solución

Descargo la imagen .jpg con el link que se me da haciendo uso del comando wget en la terminal. 
De acuerdo a la pista sobre un editor HEX investigo al respecto.
Haremos uso de un editor hex que ya trae kali, llamado hexeditor.`
`hexeditor garden.jpg` Al abrir nos encontraremos con todos los caracteres, haremos uso de un Ctrl + w y buscaremos por cadena de texto las coincidencias con picoCTF.
Encontraremos la bandera.
`picoCTF{more_than_m33ts_the_3y3657BaB2C}`
Podemos simplemente hacer un strings y al final de él estará la bandera.

## Notas adicionales

- Un editor hexadecimal, de archivos binarios o bytes; es  un programa que permite la manipulacion de los datos binarios fundamentales que constituyen un archivo de computadora.
- Puede ser usado para ver editar el contenido sin procesar de un archivo.
- Ctrl + w: Buscar en hexeditor.
- strings: Comando imprime la secuencia de caracteres imprimibles en un archivo.

## Referencias

https://en.wikipedia.org/wiki/Hex_editor