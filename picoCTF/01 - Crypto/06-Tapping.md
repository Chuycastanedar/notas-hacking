
## Descripción

Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 48247`.

## Solución

Inicio conectándome al puerto determinado.

Obtengo una cadena de caracteres donde claramente veo que es la bandera por su estructura de las llaves y las pistas, y rápidamente veo que se trata de código morse.

Simplemente voy a cyberchef en la operación From Morse Code, pego la cadena y obtengo la bandera.
`picoCTF{M0RS3C0D31SFUN1261438181}`

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=LS0gLS0tLS0gLi0uIC4uLiAuLi4tLSAtLi0uIC0tLS0tIC0uLiAuLi4tLSAuLS0tLSAuLi4gLi4tLiAuLi0gLS4gLi0tLS0gLi4tLS0gLS4uLi4gLi0tLS0gLi4uLi0gLi4uLS0gLS0tLi4gLi0tLS0gLS0tLi4gLi0tLS0

https://es.wikipedia.org/wiki/C%C3%B3digo_morse