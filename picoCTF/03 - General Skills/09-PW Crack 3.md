
## Descripción

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución

Necesitamos descargar los archivos con el comando wget.
Si ejecutamos el script con python veremos que imprime y nos pide que ingresemos la contraseña para que nos entregue la bandera. Necesitamos con el comando nano analizar el script, y si nos vamos a la parte de abajo encontramos una lista con las 7 contraseñas guardadas.
```bash
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]
```

Simplemente salimos con Ctrl X y ejecutamos el script y probamos cual de ellas es la correcta. Nos devolverá la bandera.
``` bash
JCR_07-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 2295
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}
```

## Notas adicionales


## Referencias