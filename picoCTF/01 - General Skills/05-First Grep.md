## Descripción

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Solución

Descargar el archivo en la consola
``` bash
JCR_07-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
--2025-09-01 17:07:27--  https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                 100%[=====================>]  14.21K  --.-KB/s    in 0s      

2025-09-01 17:07:27 (494 MB/s) - 'file' saved [14551/14551]
```
Aplicar el comando grep.
``` bash
JCR_07-picoctf@webshell:~$ grep 'picoCTF' file
picoCTF{grep_is_good_to_find_things_dba08a45}
```


## Notas adicionales
Comando wc te cuenta lineas caracteres y bytes en el archivo.

``` bash
JCR_07-picoctf@webshell:~$ wc file
    6   309 14551 file
```

Comando file me permite saber el tipo de archivo.

## Referencias