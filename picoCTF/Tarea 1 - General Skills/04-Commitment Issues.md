
## Descripción

I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here: challenge.zip

## Solución

Iniciamos descargando el challenge.zip que se nos da usando el comando wget y el vínculo.
Ya descargado, lo descomprimimos con el comando unzip.
Podemos observar que nos genera un repositorio de git y si revisamos el archivo veremos que este en efecto ya no contiene la bandera pero sabemos que en algún momento estuvo, por lo que hay que rescatar el repositorio al commit anterior.
Dentro del repositorio aplicamos el comando git log, el cual nos despliega el historial de commits, tomamos el último y aplicamos el git checkout "commit id" para tener la versión anterior.
Leemos el .txt y obtenemos la bandera.
``` bash
JCR_07-picoctf@webshell:~/drop-in$ git log
JCR_07-picoctf@webshell:~/drop-in$ git checkout 87b85d7dfb839b077678611280fa023d76e017b8
Previous HEAD position was 8dc5180 remove sensitive info
HEAD is now at 87b85d7 create flag
JCR_07-picoctf@webshell:~/drop-in$ cat message.txt 
picoCTF{s@n1t1z3_ea83ff2a}
```

## Notas adicionales

- git log Comando git para ver mis commits pasados
- git checkout "commit id" Comando para volver el repositorio al punto de control del commit que ingresemos

## Referencias

[The CTF Primer](https://primer.picoctf.org/#_git_version_control)