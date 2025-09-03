## Descripción

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 49574`

## Solución

Nos conectamos al servidor y puerto con el comando nc.
Al conectarnos nos regresa un código para python el cual solamente necesitamos copear.
``` bash
JCR_07-picoctf@webshell:~$ nc saturn.picoctf.net 49574
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
```
Nos desconectamos e iniciamos python en la terminal.
Pegamos el código que se nos dió.
Se devuelve la bandera lista.

``` bash
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
'picoCTF{gl17ch_m3_n07_9c42a45d}'
```
## Notas adicionales
Al copear lo que nos devuelve el servidor tenemos que mantener las comillas ''.

## Referencias
