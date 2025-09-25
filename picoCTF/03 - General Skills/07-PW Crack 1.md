
## Descripción

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.

## Solución

Necesitamos descargar los archivos con el comando wget.
Si ejecutamos el script con python veremos que imprime y nos pide que ingresemos la contraseña para que nos entregue la bandera, contraseña que no tenemos y que no se encuentra en el archivo .txt si lo leemos y probamos.
Abriremos el código del script con el comando nano y analizándolo podemos encontrar dicha contraseña en la segunda función donde se realiza la comparación. 
``` bash
if( user_pw == "1e1a"):
```

Simplemente la copeamos, salimos y pegamos al ejecutar el script y nos da la bandera.

``` bash
JCR_07-picoctf@webshell:~$ nano level1.py
JCR_07-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
```

## Notas adicionales

- Intentar siempre primero lo mas fácil, e ir planteando soluciones y descartando.


## Referencias
