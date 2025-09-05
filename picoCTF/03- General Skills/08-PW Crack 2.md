
## Descripción

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

## Solución

Necesitamos descargar los archivos con el comando wget.
Si ejecutamos el script con python veremos que imprime y nos pide que ingresemos la contraseña para que nos entregue la bandera, contraseña que no tenemos y que se encuentra encriptada en el .txt.
Abriremos el código del script con el comando nano y analizándolo podemos encontrar que dentro de la función check tenemos la comparación entre la variable que contiene la contraseña encriptada y la contraseña en un fragmento de código.
``` bash
if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
```

Solamente lo copeamos, salimos, abrimos python y lo ejecutamos, nos devolverá la contraseña.
``` bash
JCR_07-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)
'de76'
```

Con ella volvemos a ejecutar el script, la ingresamos y ya tenemos la bandera.
```bash
JCR_07-picoctf@webshell:~$ python level2.py
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
```

## Notas adicionales

- Comando python, enter, solo se pega el código.
- Salir: quit()

## Referencias
