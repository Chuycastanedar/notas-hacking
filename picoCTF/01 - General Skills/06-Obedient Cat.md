## Descripción

This file has a flag in plain sight (aka "in-the-clear").

## Solución

Tenemos que iniciar descargando el archivo copeando el vínculo y descargar con wget.

``` bash
JCR_07-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/0e428b2db9788d31189329bed089ce98/flag
--2025-09-01 17:15:28--  https://mercury.picoctf.net/static/0e428b2db9788d31189329bed089ce98/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                 100%[=====================>]      34  --.-KB/s    in 0s      

2025-09-01 17:15:28 (28.4 MB/s) - 'flag' saved [34/34]
```

Continuamos realizando simplemente un cat a flag.

```
JCR_07-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_2fd6ed29}
```

## Notas adicionales

wget para descargar archivos en terminal.
cat permite mostrar el contenido de un archivo de texto.
Todos los comandos tienen su --help para ver su ayuda.
## Referencias