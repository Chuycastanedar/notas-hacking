## Descripción

Unzip this archive and find the file named 'uber-secret.txt'

## Solución

Descargar el archivo con el comando wget, y descomprimir con unzip.
Nos despliega muchos directorios y archivos, por lo cual necesitamos buscar entre todos ellos el  'uber-secret.txt' que se nos pide.
Para ello haremos uso del comando find, que por eso se llama así el reto.

```bash
JCR_07-picoctf@webshell:~/big-zip-files$ find -name "uber-secret.txt"
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

Nos despliega la ruta de donde se encuentra nuestro archivo, por lo que nos movemos a su directorio y con un cat revisamos su contenido; lo que nos devolverá la bandera.

``` bash
JCR_07-picoctf@webshell:~/big-zip-files$ cd ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets                
JCR_07-picoctf@webshell:~/big-zip-files/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ cat uber-secret.txt 
picoCTF{f1nd_15_f457_ab443fd1}
```
## Notas adicionales

find -name "[Nombre archivo]" para buscar un archivo en multiples directorios
También podemos unir los comandos con un | para evitar el paso de movernos a la ruta.

## Referencias

[Linux find | Cómo usar el comando find de Linux - IONOS México](https://www.ionos.mx/digitalguide/servidores/configuracion/comando-linux-find/)