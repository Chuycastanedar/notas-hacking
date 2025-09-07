
## Descripción

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here: challenge.zip

## Solución

Iniciamos descargando el challenge.zip que se nos da usando el comando wget y el vínculo.
Ya descargado, lo descomprimimos con el comando unzip.
Podemos observar que nos genera un repositorio de git.
Nos cambiamos al repositorio con el comando cd y verificamos las ramas que hay con el comando que se nos proporciona en las pistas  `git branch -a `. Veremos que efectivamente tenemos las 3 ramas y el main, por lo que nos cambiamos a cada una de las 3 ramas con el comando `git checkout [Nombre de la rama]` donde en cada rama habrá un script flag.py.
Ejecutamos el script con el comando `python` en cada rama y obtendremos la bandera dividida en 3 partes.
``` bash
JCR_07-picoctf@webshell:~/drop-in$ git branch -a
JCR_07-picoctf@webshell:~/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
JCR_07-picoctf@webshell:~/drop-in$ python flag.py 
Printing the flag...
picoCTF{t3@mw0rk_
JCR_07-picoctf@webshell:~/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
JCR_07-picoctf@webshell:~/drop-in$ python flag.py 
Printing the flag...
m@k3s_th3_dr3@m_
JCR_07-picoctf@webshell:~/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
JCR_07-picoctf@webshell:~/drop-in$ python flag.py 
Printing the flag...
w0rk_6c06cec1}
```
`picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}`

## Notas adicionales

- git branch -a Comando para ver la lista de ramas en el repositorio
- git checkout [Nombre de la rama] Comando para cambiar de una rama a otra

## Referencias

[Git Switch Branch: Cómo cambiar la rama en Git](https://www.freecodecamp.org/espanol/news/git-switch-branch-como-cambiar-la-rama-en-git/)