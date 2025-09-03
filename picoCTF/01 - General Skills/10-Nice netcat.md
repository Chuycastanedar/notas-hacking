## Descripción

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 49039`, but it doesn't speak English...

## Solución
Iniciamos conectándonos al servidor y puerto con el comando nc.
Tenemos que dirigir la salida de este comando a un archivo para luego convertirlo.
Abrimos python y abrimos nuestro archivo para haciendo uso de un ciclo for recorrer el archivo y convertir a entero y chr
e imprimirlo. Resultará la llave.

``` bash
JCR_07-picoctf@webshell:~$ nc mercury.picoctf.net 49039 > file

JCR_07-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> f = open('file', 'r')
>>> for line in f:
...     line = line.strip()
...     num = int(line)
...     print(chr(num), end='')
... 
picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}
```

## Notas adicionales

- 'r' es de read, para abrir el archivo en modo lectura.

## Referencias
