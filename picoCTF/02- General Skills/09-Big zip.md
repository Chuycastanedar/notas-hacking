
## Descripción

Unzip this archive and find the flag.

## Solución

Descargamos el archivo .zip haciendo uso del comando wget.
Procedemos a descomprimir el zip con el comando unzip.
Vemo que tenemos una gran cantidad de subdirectorios y archivos .txt, por lo que necesitamos buscar la coincidencia de la bandera en todos estos archivos.
La pista nos dice que podemos hacerlo con grep, por lo que utilizaremos el modificador -r para que el grep busque recursivamente en todos los archivos de los directorios con la coincidencia de la bandera.

``` bash
JCR_07-picoctf@webshell:~$ cd big-zip-files
JCR_07-picoctf@webshell:~/big-zip-files$ grep -r "pico"
folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}

```

Nos devuelve ubicación y la bandera como coincidencia.

## Notas adicionales

Comando grep para buscarla coincidencia
-r para buscar recursivamente en todos los archivos

## Referencias

[Cómo usar el comando grep en Linux (ejemplos prácticos)](https://www.hostinger.com/mx/tutoriales/comando-grep-linux)