
## Descripción

I found this cipher in an old book. Can you figure out what it says? Connect with `nc jupiter.challenges.picoctf.org 5726`.

## Solución

Inicio conectándome al puerto determinado.

Obtengo el texto encriptado dentro del que claramente se observa la bandera cifrada, puesto que observamos su estructura.

Al probar descifrar este texto con el anterior algoritmo ROT13 y sus derivados no lo logro.

Se que lo puedo descifrar con el Vigenère, pero no tengo la llave.

Utilizamos una herramienta de Viegenère solver, para descifrar este texto. Ingreso el texto y obtengo la llave y la bandera:
`flag`
`picoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}`

## Notas adicionales

- Análisis de frecuencias: Forma de crypto análisis que intenta descifrar el texto en base a la frecuencia de las letras.

## Referencias

https://es.wikipedia.org/wiki/An%C3%A1lisis_de_frecuencias

https://www.guballa.de/vigenere-solver