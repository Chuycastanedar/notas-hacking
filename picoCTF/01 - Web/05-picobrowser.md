
## Descripción

This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/50522/` ([link](https://jupiter.challenges.picoctf.org/problem/50522/)) or http://jupiter.challenges.picoctf.org:50522

## Solución

Ingreso a la página web y en cuanto interactúo con el botón Flag me aparece el aviso de error y que no tengo picobrowser.
Inspecciono el código fuente y no encuentro nada, pero logro dar con la información de User Agent, aún así no puedo cambiarlo desde mi navegador.
Desde mi terminal utilizo el comando curl -s para acceder al link, asigno el User Agent como picobrowser y dirijo la salida con un pipe y grep a pico para filtrar más fácil la bandera.
Obtengo la bandera.
``` bash
JCR_07-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/50522/ -H "User-Agent: picobrowser" | grep picoCTF
JCR_07-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/50522/ -H User-Agent:"picobrowser" | grep picoCTF
JCR_07-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/50522/ -H "User~Agent: picobrowser" | grep picoCTF
JCR_07-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/50522/flag -H "User-Agent: picobrowser" | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}</code></p>
```

## Notas adicionales

- User Agent es un encabezado que se manda con la petición, una cadena característica que le permite al servidor y a la red identificarse a si mismos para saber el navegador del cliente, sistema operativo, vendedor y versión que esta solicitando el recurso al servidor.
- curl es un cliente de consola para obtener recursos web, como si fuera un navergador de consola.

## Referencias
