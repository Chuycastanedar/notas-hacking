## Descripción

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

## Solución

Inicio copiando el vínculo del archivo, para luego ir a la terminal y descargando con el comando wget.
``` bash
JCR_07-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
--2025-09-03 16:32:55--  https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings              100%[=====================>] 757.84K  1.87MB/s    in 0.4s    

2025-09-03 16:32:56 (1.87 MB/s) - 'strings' saved [776032/776032]
```

Con el comando strings abrimos el archivo strings y nos imprimirá todas las cadenas. Pero como el contenido es grande, vamos a utilizar un pipe para dirigir la salida del comando strings en el archivo strings a un grep para filtrar solo las cadenas con "pico" de coincidencia y nos dará la bandera.

``` bash
JCR_07-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_d66c7bb7}
```
## Notas adicionales
Comando strings despliega las cadenas imprimibles en archivos.
Comando reset reinicia la terminal.
Para ejecutar un archivo. exe se utiliza el comando ./[NOMBRE DEL ARCHIVO]
chmod +x [Nombre del archivo] añade permisos al binario para ejecutarse
chmod -= [Nombre del archivo] devuelve el archivo a como estaba antes
## Referencias

[strings(1) - Linux man page](https://linux.die.net/man/1/strings)