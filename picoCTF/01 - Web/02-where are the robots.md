
## Descripción

Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474

## Solución

Inicio entrando al sitio web del que se nos proporciona.
Me encuentro con un sitio con un par de etiquetas pero vacío, y al inspeccionar su código no encuentro nada.
Como se menciona en el reto sobre robots intentamos buscar archivo robots para investigar.
Vemos que existe un archivo robots.txt
Asumiendo que lo tenemos intentamos abrirlo en el Url. `https://jupiter.challenges.picoctf.org/problem/36474/robots.txt`
Se accede a él y efectivamente observamos una ruta, que está es a la que se supone que no se quiere que se acceda.
La agregamos al Url y accedemos a ella. `https://jupiter.challenges.picoctf.org/problem/36474/477ce.html`
Hemos encontrado la bandera: `picoCTF{ca1cu1at1ng_Mach1n3s_477ce}`.

## Notas adicionales

- robots.txt se usa para controlar a que archivos pueden acceder los rastreadores.
- En el se ponen las instrucciones necesarias para decirle que rutas no queremos que se accedan.

## Referencias

[Introducción a los archivos robots.txt | Centro de la Búsqueda de Google  |  Documentation  |  Google for Developers](https://developers.google.com/search/docs/crawling-indexing/robots/intro?hl=es)