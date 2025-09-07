
## Descripción

What was I last working on? 
I remember writing a note to help me remember...You can download the challenge files here: challenge.zip

## Solución

Iniciamos descargando el challenge.zip que se nos da usando el comando wget y el vínculo.
Ya descargado, lo descomprimimos con el comando unzip.
Podemos observar que nos genera un repositorio de git y si revisamos el archivo veremos que este en efecto no contiene la bandera pero indica que busquemos en el historial de commits.
Dentro del repositorio aplicamos el comando git log, el cual nos despliega el historial de commits y en efecto dentro de el encontramos la bandera.
``` bash
JCR_07-picoctf@webshell:~/drop-in$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...JCR_07-picoctf@webshell:~/drop-in$ ^C
JCR_07-picoctf@webshell:~/drop-in$ git log
```

## Notas adicionales

- git log Comando git para ver mis commits pasados
- git checkout "commit id" Comando para volver el repositorio al punto de control del commit que ingresemos

## Referencias

[The CTF Primer](https://primer.picoctf.org/#_git_version_control)