
## Descripción

Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.

## Solución

Solamente necesitamos descargar el archivo .py haciendo uso del comando wget.
Ya descargado como es un archivo python simplemente lo ejecutamos con el comando python y nos devolverá la bandera.

``` bash
JCR_07-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2025-09-05 05:14:57--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.18, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                   100%[=====================================================================================>]     270  --.-KB/s    in 0s      

2025-09-05 05:14:58 (216 MB/s) - 'runme.py' saved [270/270]

JCR_07-picoctf@webshell:~$ python runme.py 
picoCTF{run_s4n1ty_run}
```

## Notas adicionales



## Referencias