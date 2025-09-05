
## Descripción

Fix the syntax error in the Python script to print the flag.

## Solución

Necesitamos descargar el script con el comando wget.
Si lo ejecutamos con python veremos que no nos lo permite y nos manda un error en la línea 22, sobre un '='.
Necesitamos corregir este error, para ello utilizaremos el comando nano [Nombre del archivo.py].
Ubicamos el error que nos marcó en la línea 22 en un if, simplemente agregamos otro '=' y salimos con Ctrl X, luego enter.
Si corregimos adecuadamente el error al volver a ejecutar lo hará correctamente y nos regresa la bandera.

``` bash
JCR_07-picoctf@webshell:~$ python fixme2.py 
  File "/home/JCR_07-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
JCR_07-picoctf@webshell:~$ nano fixme2.py 
JCR_07-picoctf@webshell:~$ python fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

## Notas adicionales

- nano se utiliza para ver y modificar el script .py en la terminal.
- nano nos proporciona ahi los comandos para interactuar

## Referencias
