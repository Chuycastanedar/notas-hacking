
## Descripción

[🥛](http://mercury.picoctf.net:16940/)

## Solución

Inicio observando que solamente tengo un emoji con un link en la descripción del reto.
Abro el sitio web y al inspeccionarlo veo que solamente es una imagen que interactua de acuerdo al movimiento del mouse, leo la pista que me dice que vea la categría del reto por lo que descargo la imagen en mi computadora para analizarla.

Investigo y uso la herramienta zsteg, primero la descargo:
`gem install zsteg`

`zsteg concat_v.png`

Obtengo la bandera: `picoCTF{imag3_m4n1pul4t10n_sl4p5}`


## Notas adicionales

- zsteg Description: Detect stegano-hidden data in PNG & BMP. zsteg is a tool that can detect LSB steganography in PNG & BMP, zlib-compressed data.


## Referencias

https://cybersectools.com/tools/zsteg