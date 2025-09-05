
## Descripción

Fix the syntax error in this Python script to print the flag.

## Solución

Necesitamos descargar el script con el comando wget.
Si lo ejecutamos con python veremos que no nos lo permite y nos manda un error de indentación.
Necesitamos corregir este error, para ello utilizaremos el comando nano [Nombre del archivo.py].
Ubicamos el error que nos marcó en la línea 20 y salimos con Ctrl X, luego enter.
Si corregimos adecuadamente el error al volver a ejecutar lo hará correctamente y nos regresa la bandera.

``` bash
README.txt  fixme1.py
JCR_07-picoctf@webshell:~$ python fixme1.py 
  File "/home/JCR_07-picoctf/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
JCR_07-picoctf@webshell:~$ nano fixme1.py 
JCR_07-picoctf@webshell:~$ python fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
```


## Notas adicionales

- nano se utiliza para ver y modificar el script .py en la terminal.
- nano nos proporciona ahi los comandos para interactuar

## Referencias
